---
title: Configurare la ricerca di Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Informazioni su come configurare la ricerca in un ambiente multi-geografico. Solo alcuni client, come OneDrive for business, possono restituire risultati in un ambiente multi-geografico.
ms.openlocfilehash: e213e93cfbc967a723b4d27f4b36a83fe6687da9
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547153"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="894b5-104">Configurare la ricerca di Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="894b5-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="894b5-105">In un ambiente multi-geografico, ogni posizione geografica ha un proprio indice di ricerca e un Centro ricerche.</span><span class="sxs-lookup"><span data-stu-id="894b5-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="894b5-106">Quando un utente effettua una ricerca, la query viene inviata a tutti gli indici e i risultati restituiti vengono aggregati.</span><span class="sxs-lookup"><span data-stu-id="894b5-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="894b5-107">Ad esempio, un utente in una posizione geografica può cercare contenuto archiviato in un'altra posizione geografica o il contenuto di un sito di SharePoint che è limitato a una posizione geografica diversa.</span><span class="sxs-lookup"><span data-stu-id="894b5-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="894b5-108">Se l'utente ha accesso a tale contenuto, la ricerca mostrerà il risultato.</span><span class="sxs-lookup"><span data-stu-id="894b5-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="894b5-109">Quali client di ricerca funzionano in un ambiente multi-geografico?</span><span class="sxs-lookup"><span data-stu-id="894b5-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="894b5-110">Questi client possono restituire i risultati di tutte le posizioni geografiche:</span><span class="sxs-lookup"><span data-stu-id="894b5-110">These clients can return results from all geo locations:</span></span>

- <span data-ttu-id="894b5-111">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="894b5-111">OneDrive for Business</span></span>
- <span data-ttu-id="894b5-112">Delve</span><span class="sxs-lookup"><span data-stu-id="894b5-112">Delve</span></span>
- <span data-ttu-id="894b5-113">Home page di SharePoint</span><span class="sxs-lookup"><span data-stu-id="894b5-113">The SharePoint home page</span></span>
- <span data-ttu-id="894b5-114">Centro ricerche</span><span class="sxs-lookup"><span data-stu-id="894b5-114">The Search Center</span></span>
- <span data-ttu-id="894b5-115">Applicazioni di ricerca personalizzate che utilizzano l'API del servizio di ricerca di SharePoint</span><span class="sxs-lookup"><span data-stu-id="894b5-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="894b5-116">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="894b5-116">OneDrive for Business</span></span>

<span data-ttu-id="894b5-117">Non appena viene configurato l'ambiente multi-geografico, gli utenti che cercano in OneDrive ottengono i risultati di tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="894b5-118">Delve</span><span class="sxs-lookup"><span data-stu-id="894b5-118">Delve</span></span>

<span data-ttu-id="894b5-119">Non appena viene configurato l'ambiente multi-geografico, gli utenti che cercano in Delve ottengono risultati da tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="894b5-120">Il feed di Delve e la scheda profilo mostrano solo le anteprime dei file archiviati in una posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="894b5-120">The Delve feed and the profile card only show previews of files that are stored in the central location.</span></span> <span data-ttu-id="894b5-121">Per i file archiviati nelle posizioni satellite, verrà visualizzata l'icona del tipo di file.</span><span class="sxs-lookup"><span data-stu-id="894b5-121">For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="894b5-122">Home page di SharePoint</span><span class="sxs-lookup"><span data-stu-id="894b5-122">The SharePoint home page</span></span>

<span data-ttu-id="894b5-p105">Non appena l'ambiente multi-geografico viene configurato, gli utenti possono vedere le notizie, i siti recenti e i siti seguiti di posizioni geografiche diverse nella propria home page di SharePoint. Se usano la casella di ricerca nella home page di SharePoint, aggregheranno tutti i risultati delle posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-p105">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page. If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="894b5-125">Centro ricerche</span><span class="sxs-lookup"><span data-stu-id="894b5-125">The Search Center</span></span>

<span data-ttu-id="894b5-p106">Dopo che l'ambiente multi-geografico viene configurato, ogni Centro ricerche continua a mostrare solo i risultati della relativa posizione geografica. Gli amministratori devono [modificare le impostazioni di ogni Centro ricerche](#_Set_up_a_1) per generare i risultati di tutte le posizioni geografiche. Successivamente gli utenti che usano il Centro ricerche potranno ottenere i risultati aggregati di tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-p106">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location. Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations. Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="894b5-129">Applicazioni di ricerca personalizzate</span><span class="sxs-lookup"><span data-stu-id="894b5-129">Custom search applications</span></span>

<span data-ttu-id="894b5-p107">In genere, le applicazioni di ricerca personalizzate interagiscono con le API REST del servizio di ricerca di SharePoint esistenti. Per ottenere risultati di tutte le posizioni geografiche o solo di alcune, l'applicazione deve [chiamare l'API e includere i nuovi parametri di query Multi-Geo](#_Get_custom_search) nella richiesta. In questo modo, la query viene estesa a tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-p107">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs. To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request. This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="894b5-133">In che modo la ricerca è diversa in un ambiente multi-geografico?</span><span class="sxs-lookup"><span data-stu-id="894b5-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="894b5-134">Alcune delle funzionalità di ricerca già note potrebbero funzionare diversamente in un ambiente multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="894b5-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="894b5-135"><strong>Caratteristica</strong></span><span class="sxs-lookup"><span data-stu-id="894b5-135"><strong>Feature</strong></span></span></th>
<th align="left"><span data-ttu-id="894b5-136"><strong>Come funziona</strong></span><span class="sxs-lookup"><span data-stu-id="894b5-136"><strong>How it works</strong></span></span></th>
<th align="left"><span data-ttu-id="894b5-137"><strong>Soluzione</strong></span><span class="sxs-lookup"><span data-stu-id="894b5-137"><strong>Workaround</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="894b5-138">Risultati evidenziati</span><span class="sxs-lookup"><span data-stu-id="894b5-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="894b5-139">È possibile creare regole di query con risultati promossi a diversi livelli: per l'intero tenant, per una raccolta siti o per un sito.</span><span class="sxs-lookup"><span data-stu-id="894b5-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="894b5-140">In un ambiente multi-geo definire i risultati promossi a livello di tenant, per promuovere i risultati nei Centri ricerche di tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="894b5-141">Se si desidera soltanto convertire i risultati nel Centro ricerche che si trova nella posizione geografica della raccolta siti o del sito, definire i risultati promossi a livello della raccolta siti o del sito.</span><span class="sxs-lookup"><span data-stu-id="894b5-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="894b5-142">Questi risultati non sono promossi in altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="894b5-143">Se non sono necessari diversi risultati evidenziati per ogni posizione geografica, ad esempio direttive diverse per le trasferte di lavoro, è consigliabile definire i risultati evidenziati a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="894b5-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="894b5-144">Criteri di affinamento ricerca</span><span class="sxs-lookup"><span data-stu-id="894b5-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="894b5-p109">La ricerca restituisce i criteri di affinamento di tutte le posizioni geografiche di un tenant e poi li aggrega. L'aggregazione è approssimativa e viene eseguita secondo il principio "best effort", quindi i conteggi dei criteri di affinamento potrebbero non essere precisi. Per la maggior parte degli scenari di ricerca questo livello di approssimazione è sufficiente. </span><span class="sxs-lookup"><span data-stu-id="894b5-p109">Search returns refiners from all the geo locations of a tenant and then aggregates them. The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate. For most search-driven scenarios, this accuracy is sufficient. </span></span></td>
<td align="left"><span data-ttu-id="894b5-148">Per le applicazioni basate sulla ricerca che richiedono criteri di affinamento precisi, è necessario inviare la query separatamente a ogni posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="894b5-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="894b5-149">La ricerca multi-geografica non supporta il bucket di criteri di affinamento numerici.</span><span class="sxs-lookup"><span data-stu-id="894b5-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="894b5-150">Utilizzare il <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">parametro "discretizzare"</a> per i perfezionamenti numerici.</span><span class="sxs-lookup"><span data-stu-id="894b5-150">Use the <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="894b5-151">ID documenti</span><span class="sxs-lookup"><span data-stu-id="894b5-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="894b5-152">Se si decide di sviluppare un'applicazione basata sulla ricerca che usa gli ID dei documenti, occorre tenere presente che tali ID non sono univoci nell'intero ambiente multi-geografico, ma solo all'interno di una singola posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="894b5-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="894b5-153">È stata aggiunta una colonna che identifica la posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="894b5-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="894b5-154">Usare questa colonna per ottenere l'univocità.</span><span class="sxs-lookup"><span data-stu-id="894b5-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="894b5-155">Questa colonna è denominata "GeoLocationSource".</span><span class="sxs-lookup"><span data-stu-id="894b5-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="894b5-156">Numero di risultati</span><span class="sxs-lookup"><span data-stu-id="894b5-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="894b5-157">La pagina dei risultati della ricerca mostra i risultati combinati ottenuti dalle posizioni geografiche, ma non è possibile includere più di 500 risultati.</span><span class="sxs-lookup"><span data-stu-id="894b5-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="894b5-158">Ricerca ibrida</span><span class="sxs-lookup"><span data-stu-id="894b5-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="894b5-159">In un ambiente SharePoint ibrido con <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">Ricerca ibrida nel cloud</a>, il contenuto locale viene aggiunto all'indice di Microsoft 365 della posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="894b5-159">In a hybrid SharePoint environment with <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="894b5-160">Cosa non è supportato per la ricerca in un ambiente multi-geografico?</span><span class="sxs-lookup"><span data-stu-id="894b5-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="894b5-161">Alcune delle funzionalità di ricerca già note non sono supportate in un ambiente multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="894b5-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="894b5-162"><strong>Funzionalità di ricerca</strong></span><span class="sxs-lookup"><span data-stu-id="894b5-162"><strong>Search feature</strong></span></span></th>
<th align="left"><span data-ttu-id="894b5-163"><strong>Nota</strong></span><span class="sxs-lookup"><span data-stu-id="894b5-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="894b5-164">Autenticazione solo app</span><span class="sxs-lookup"><span data-stu-id="894b5-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="894b5-165">L'autenticazione solo app (accesso con privilegi dai servizi) non è supportata nella ricerca multi-geografica.</span><span class="sxs-lookup"><span data-stu-id="894b5-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="894b5-166">Utenti guest</span><span class="sxs-lookup"><span data-stu-id="894b5-166">Guest users</span></span></td>
<td align="left"><span data-ttu-id="894b5-167">Gli utenti guest ottengono solo i risultati della posizione geografica dove effettuano la ricerca.</span><span class="sxs-lookup"><span data-stu-id="894b5-167">Guest users only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="894b5-168">Come funziona la ricerca in un ambiente multi-geografico?</span><span class="sxs-lookup"><span data-stu-id="894b5-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="894b5-169">Tutti i client di ricerca usano le API REST del servizio di ricerca di SharePoint per interagire con gli indici di ricerca.</span><span class="sxs-lookup"><span data-stu-id="894b5-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

![Diagramma che Mostra come le API REST Search di SharePoint interagiscono con gli indici di ricerca](../media/configure-search-for-multi-geo-image1-1.png)

1. <span data-ttu-id="894b5-171">Un client di ricerca chiama l'endpoint REST Ricerca con la proprietà di query EnableMultiGeoSearch= true.</span><span class="sxs-lookup"><span data-stu-id="894b5-171">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="894b5-172">La query viene inviata a tutte le posizioni geografiche del tenant.</span><span class="sxs-lookup"><span data-stu-id="894b5-172">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="894b5-173">I risultati della ricerca di ogni posizione geografica vengono aggregati e classificati.</span><span class="sxs-lookup"><span data-stu-id="894b5-173">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="894b5-174">Il client ottiene risultati della ricerca unificati.</span><span class="sxs-lookup"><span data-stu-id="894b5-174">The client gets unified search results.</span></span>

<span data-ttu-id="894b5-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Si noti che Microsoft non unisce i risultati della ricerca fino a quando non si ricevono i risultati da tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="894b5-176">Questo significa che le ricerche multi-geo hanno una latenza maggiore rispetto alle ricerche in un ambiente che ha una sola posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="894b5-176">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="894b5-177">Fare in modo che un Centro ricerche mostri i risultati di tutte le posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="894b5-177">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="894b5-178">Ogni Centro ricerche dispone di diverse verticali ed è necessario configurarle singolarmente.</span><span class="sxs-lookup"><span data-stu-id="894b5-178">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1. <span data-ttu-id="894b5-179">Assicurarsi di avere eseguito questi passaggi con un account che dispone dell'autorizzazione per modificare la pagina dei risultati della ricerca e la web part Risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="894b5-179">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2. <span data-ttu-id="894b5-180">Andare alla pagina dei risultati della ricerca (vedere l'[elenco](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) delle pagine di risultati della ricerca).</span><span class="sxs-lookup"><span data-stu-id="894b5-180">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3. <span data-ttu-id="894b5-p112">Selezionare la verticale da configurare, fare clic sull'icona a forma di ingranaggio **Impostazioni** in alto a destra, quindi fare clic su **Modifica pagina**. La pagina dei risultati della ricerca si apre in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="894b5-p112">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**. The search results page opens in Edit mode.</span></span>

   ![Modificare la selezione delle pagine nelle impostazioni](../media/configure-search-for-multi-geo-image2.png)

4. <span data-ttu-id="894b5-184">Nella web part Risultati della ricerca, spostare il puntatore sull'angolo in alto a destra della web part, fare clic sulla freccia, quindi fare clic su **Modifica web part** nel menu.  </span><span class="sxs-lookup"><span data-stu-id="894b5-184">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="894b5-185">Si apre il riquadro degli strumenti della web part Risultati della ricerca sotto la barra multifunzione in alto a destra nella pagina.</span><span class="sxs-lookup"><span data-stu-id="894b5-185">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span>

   ![Modificare la selezione di una Web part](../media/configure-search-for-multi-geo-image3.png)

5. <span data-ttu-id="894b5-187">Nella riquadro degli strumenti della web part, nella sezione **Impostazioni**, in **Impostazioni controllo risultati**, selezionare **Mostra risultati Multi-Geo** affinché la web part Risultati della ricerca mostri i risultati di tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-187">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

6. <span data-ttu-id="894b5-188">Fare clic su **OK** per salvare la modifica e chiudere il riquadro degli strumenti della web part.</span><span class="sxs-lookup"><span data-stu-id="894b5-188">Click **OK** to save your change and close the Web Part tool pane.</span></span>

7. <span data-ttu-id="894b5-189">Verificare le modifiche apportate alla web part Risultati della ricerca facendo clic su **Controllo** nella scheda Pagina del menu principale.</span><span class="sxs-lookup"><span data-stu-id="894b5-189">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

8. <span data-ttu-id="894b5-190">Pubblicare le modifiche usando il collegamento fornito nella nota in alto nella pagina.</span><span class="sxs-lookup"><span data-stu-id="894b5-190">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="894b5-191">Fare in modo che le applicazioni di ricerca personalizzate mostrino risultati di tutte o di alcune posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="894b5-191">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="894b5-p114">Per ottenere i risultati di tutte o alcune posizioni geografiche nelle applicazioni di ricerca personalizzate, è necessario specificare i parametri di query con la richiesta all'API REST del servizio di ricerca di SharePoint. A seconda dei parametri della query, la query viene inviata a tutte le posizioni geografiche o solo ad alcune. Ad esempio, se serve inviare la query solo a un sottoinsieme di posizioni geografiche per trovare informazioni pertinenti, è possibile estendere la query solo ad esse. Se la richiesta ha esito positivo, l'API REST del servizio di ricerca di SharePoint restituisce i dati della risposta.</span><span class="sxs-lookup"><span data-stu-id="894b5-p114">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API. Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations. For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these. If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

### <a name="requirement"></a><span data-ttu-id="894b5-196">Requisito</span><span class="sxs-lookup"><span data-stu-id="894b5-196">Requirement</span></span>

<span data-ttu-id="894b5-p115">Per ogni posizione geografica è necessario verificare che a tutti gli utenti dell'organizzazione sia stato concesso il livello di autorizzazioni **Lettura** per il sito Web radice, ad esempio contoso**APAC**.sharepoint.com/ e contoso**EU**.sharepoint.com/. [Informazioni sulle autorizzazioni](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span><span class="sxs-lookup"><span data-stu-id="894b5-p115">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso**APAC**.sharepoint.com/ and contoso**EU**.sharepoint.com/). [Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="894b5-199">Parametri di query</span><span class="sxs-lookup"><span data-stu-id="894b5-199">Query parameters</span></span>

<span data-ttu-id="894b5-200">EnableMultiGeoSearch - questo è un valore Booleano che specifica se la query debba essere estesa agli indici di altre posizioni geografiche del tenant multi-geo.</span><span class="sxs-lookup"><span data-stu-id="894b5-200">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="894b5-201">Impostare su **true** per estendere la query, su **false** per non estendere la query.</span><span class="sxs-lookup"><span data-stu-id="894b5-201">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="894b5-202">Se non si include questo parametro, il valore predefinito è **false**, tranne quando si esegue una chiamata all'API REST su un sito che usa il modello Centro ricerche organizzazione. In tal caso, il valore predefinito è **true**.</span><span class="sxs-lookup"><span data-stu-id="894b5-202">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="894b5-203">Se si usa questo parametro in un ambiente non multi-geografico, il parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="894b5-203">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="894b5-204">ClientType - Questa è una stringa.</span><span class="sxs-lookup"><span data-stu-id="894b5-204">ClientType - This is a string.</span></span> <span data-ttu-id="894b5-205">Immettere un nome univoco di client per ogni applicazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="894b5-205">Enter a unique client name for each search application.</span></span> <span data-ttu-id="894b5-206">Se non si include questo parametro, la query non viene estesa a diverse posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-206">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="894b5-207">MultiGeoSearchConfiguration - Questo è un elenco facoltativo di quali posizioni geografiche devono essere estese alla query quando **EnableMultiGeoSearch** è impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="894b5-207">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="894b5-208">Se non si include questo parametro o lo si lascia vuoto, la query non viene estesa a diverse posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="894b5-208">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="894b5-209">Per ogni posizione geografica, immettere quanto segue, in formato JSON:</span><span class="sxs-lookup"><span data-stu-id="894b5-209">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="894b5-210">Elemento</span><span class="sxs-lookup"><span data-stu-id="894b5-210">Item</span></span></th>
<th align="left"><span data-ttu-id="894b5-211">Descrizione</span><span class="sxs-lookup"><span data-stu-id="894b5-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="894b5-212">DataLocation</span><span class="sxs-lookup"><span data-stu-id="894b5-212">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="894b5-213">La posizione geografica, ad esempio NAM.</span><span class="sxs-lookup"><span data-stu-id="894b5-213">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="894b5-214">EndPoint</span><span class="sxs-lookup"><span data-stu-id="894b5-214">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="894b5-215">L'endpoint a cui connettersi, ad esempio https://contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="894b5-215">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="894b5-216">SourceId</span><span class="sxs-lookup"><span data-stu-id="894b5-216">SourceId</span></span></td>
<td align="left"><span data-ttu-id="894b5-217">Il GUID dell'origine dei risultati, ad esempio B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span><span class="sxs-lookup"><span data-stu-id="894b5-217">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="894b5-p119">Se si omette DataLocation o EndPoint oppure se DataLocation è duplicato, la richiesta ha esito negativo. [È possibile ottenere informazioni sull'endpoint delle posizioni geografiche di un tenant utilizzando Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).</span><span class="sxs-lookup"><span data-stu-id="894b5-p119">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails. [You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="894b5-220">Dati di risposta</span><span class="sxs-lookup"><span data-stu-id="894b5-220">Response data</span></span>

<span data-ttu-id="894b5-p120">MultiGeoSearchStatus - Si tratta di una proprietà che restituisce l'API Ricerca di SharePoint in risposta a una richiesta. Il valore della proprietà è una stringa e fornisce le informazioni seguenti sui risultati restituiti dall'API Ricerca di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="894b5-p120">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request. The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="894b5-223">Valore</span><span class="sxs-lookup"><span data-stu-id="894b5-223">Value</span></span></th>
<th align="left"><span data-ttu-id="894b5-224">Descrizione</span><span class="sxs-lookup"><span data-stu-id="894b5-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="894b5-225">Full</span><span class="sxs-lookup"><span data-stu-id="894b5-225">Full</span></span></td>
<td align="left"><span data-ttu-id="894b5-226">Risultati completi da <strong>tutte</strong> le posizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="894b5-226">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="894b5-227">Partial</span><span class="sxs-lookup"><span data-stu-id="894b5-227">Partial</span></span></td>
<td align="left"><span data-ttu-id="894b5-p121">Risultati parziali da una o più posizioni geografiche. I risultati non sono completi a causa di un errore temporaneo.</span><span class="sxs-lookup"><span data-stu-id="894b5-p121">Partial results from one or more geo locations. The results are incomplete due to a transient error.</span></span></td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="894b5-230">Query che usa il servizio REST</span><span class="sxs-lookup"><span data-stu-id="894b5-230">Query using the REST service</span></span>

<span data-ttu-id="894b5-p122">Con una richiesta GET, si specificano i parametri di query nell'URL. Con una richiesta POST, i parametri della query vengono ignorati nel corpo nel formato JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="894b5-p122">With a GET request, you specify the query parameters in the URL. With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>

#### <a name="request-headers"></a><span data-ttu-id="894b5-233">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="894b5-233">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="894b5-234">Name</span><span class="sxs-lookup"><span data-stu-id="894b5-234">Name</span></span></th>
<th align="left"><span data-ttu-id="894b5-235">Valore</span><span class="sxs-lookup"><span data-stu-id="894b5-235">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="894b5-236">Content-Type</span><span class="sxs-lookup"><span data-stu-id="894b5-236">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="894b5-237">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="894b5-237">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="894b5-238">Esempio di richiesta GET estesa a **tutte** le posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="894b5-238">Sample GET request that's fanned out to **all** geo locations</span></span>

<span data-ttu-id="894b5-239">https:// \<tenant\> / \_ API/search/query? QueryText =' SharePoint ' &Properties =' EnableMultiGeoSearch: true ' &ClientType =' My \_ client \_ ID '</span><span class="sxs-lookup"><span data-stu-id="894b5-239">https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'</span></span>

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="894b5-240">Esempio di richiesta GET estesa ad **alcune** posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="894b5-240">Sample GET request to fan out to **some** geo locations</span></span>

<span data-ttu-id="894b5-241">https:// \<tenant\> / \_ API/search/query? QueryText =' site ' &ClientType =' my_client_id ' &Properties =' EnableMultiGeoSearch: true, MultiGeoSearchConfiguration: [{datalocation \\ : "Nam" \\ , endpoint \\ : "https \\ ://contosoNAM.SharePoint.com" \\ , SourceID \\ : "B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ , {datalocation \\ : "Can" \\ , endpoint \\ : "https \\ ://contosoCAN.SharePoint-DF.com"}]'</span><span class="sxs-lookup"><span data-stu-id="894b5-241">https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'</span></span>

> [!NOTE]
> <span data-ttu-id="894b5-242">Le virgole e i due punti nell'elenco di posizioni geografiche per la proprietà MultiGeoSearchConfiguration sono preceduti dalla **barra rovesciata**.</span><span class="sxs-lookup"><span data-stu-id="894b5-242">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="894b5-243">Questo perché le richieste GET usano i due punti per separare le proprietà e le virgole per separare gli argomenti delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="894b5-243">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="894b5-244">Senza la barra rovesciata come carattere di escape, la proprietà MultiGeoSearchConfiguration viene interpretata in modo errato.</span><span class="sxs-lookup"><span data-stu-id="894b5-244">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="894b5-245">Esempio di richiesta POST estesa a **tutte** le posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="894b5-245">Sample POST request that's fanned out to **all** geo locations</span></span>

```text
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="894b5-246">Esempio di richiesta POST estesa ad **alcune** posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="894b5-246">Sample POST request that's fanned out to **some** geo locations</span></span>

```text
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a><span data-ttu-id="894b5-247">Query che usa CSOM</span><span class="sxs-lookup"><span data-stu-id="894b5-247">Query using CSOM</span></span>

<span data-ttu-id="894b5-248">Esempio di query CSOM estesa a **tutte** le posizioni geografiche:</span><span class="sxs-lookup"><span data-stu-id="894b5-248">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

```text
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery["EnableMultiGeoSearch"] = true;
```
