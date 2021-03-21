---
title: Diagnosi dei problemi delle prestazioni con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: In questo articolo viene illustrato come diagnosticare i problemi comuni relativi al sito di SharePoint Online utilizzando gli strumenti di sviluppo di Internet Explorer.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927613"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="2cb29-103">Diagnosi dei problemi delle prestazioni con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2cb29-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="2cb29-104">In questo articolo viene illustrato come diagnosticare i problemi comuni relativi al sito di SharePoint Online utilizzando gli strumenti di sviluppo di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2cb29-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="2cb29-105">Esistono tre modi per identificare che una pagina in un sito di SharePoint Online presenta di un problema di prestazioni con le personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2cb29-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="2cb29-106">Il network monitor della barra degli strumenti F12</span><span class="sxs-lookup"><span data-stu-id="2cb29-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="2cb29-107">Confronto di una linea di base non personalizzata</span><span class="sxs-lookup"><span data-stu-id="2cb29-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="2cb29-108">Metrica dell'intestazione delle risposte di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2cb29-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="2cb29-109">In questo argomento viene descritto come utilizzare ciascuno di questi metodi per diagnosticare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2cb29-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="2cb29-110">Una volta individuata la causa del problema, è possibile lavorare a una soluzione utilizzando gli articoli sul miglioramento delle prestazioni di SharePoint disponibili in https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="2cb29-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="2cb29-111">Utilizzo della barra degli strumenti F12 per diagnosticare le prestazioni in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2cb29-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="2cb29-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb29-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="2cb29-p102">In questo articolo si utilizza Internet Explorer 11. Le versioni degli strumenti di sviluppo F12 su altri browser dispongono di caratteristiche simili, anche se potrebbero apparire leggermente diversi. Per informazioni sugli strumenti di sviluppo F12, vedere:</span><span class="sxs-lookup"><span data-stu-id="2cb29-p102">In this article we use Internet Explorer 11. Versions of the F12 developer tools on other browsers have similar features though they may look slightly different. For information on the F12 developer tools, see:</span></span>
  
- <span data-ttu-id="2cb29-116">[Novità di F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="2cb29-116">[What's new in F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span></span>

- <span data-ttu-id="2cb29-117">[Uso degli strumenti di sviluppo F12](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="2cb29-117">[Using the F12 developer tools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span></span>

<span data-ttu-id="2cb29-118">Per visualizzare gli strumenti di sviluppo premere **F12**, quindi fare clic sull'icona Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="2cb29-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Schermata dell'icona Wi-Fi di Strumenti di sviluppo F12](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="2cb29-p103">Nella scheda **Rete**, premere il pulsante verde di riproduzione per caricare la pagina. Lo strumento restituisce tutti i file che il browser richiede per ottenere la pagina richiesta dall'utente. La schermata seguente mostra un elenco di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="2cb29-p103">On the **Network** tab, press the green play button to load a page. The tool returns all of the files that the browser requests in order to get the page you asked for. The following screen shot shows one such list.</span></span>
  
![Schermata dell'elenco di file restituito con una richiesta di pagina.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="2cb29-124">È inoltre possibile visualizzare i tempi di download dei file sul lato destro, come illustrato in questa schermata.</span><span class="sxs-lookup"><span data-stu-id="2cb29-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagramma che mostra il tempo necessario per il caricamento delle pagine richieste da SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="2cb29-126">In questo modo, si ottiene una rappresentazione visiva del tempo impiegato per caricare il file.</span><span class="sxs-lookup"><span data-stu-id="2cb29-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="2cb29-127">La linea verde segnala quando la pagina è pronta per il rendering del browser.</span><span class="sxs-lookup"><span data-stu-id="2cb29-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="2cb29-128">Ciò può fornire una visualizzazione rapida dei file diversi che possono rallentare i caricamenti delle pagine sul sito.</span><span class="sxs-lookup"><span data-stu-id="2cb29-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="2cb29-129">Configurazione di una linea di base non personalizzata per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2cb29-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="2cb29-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb29-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="2cb29-131">Il modo migliore per determinare i punti deboli delle prestazioni del sito è configurare una raccolta siti completamente completa in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2cb29-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="2cb29-132">In questo modo è possibile confrontare tutti i vari aspetti del proprio sito con quello che si otterrebbe senza nessuna personalizzazione della pagina.</span><span class="sxs-lookup"><span data-stu-id="2cb29-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="2cb29-133">L'home page di OneDrive for Business è un buon esempio di una raccolta siti separata che di solito non dispone di personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2cb29-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="2cb29-134">Visualizzazione delle informazioni di intestazione della risposta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cb29-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="2cb29-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb29-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="2cb29-136">In SharePoint Online, è possibile accedere alle informazioni inviate al browser nell'intestazione della risposta per ogni file.</span><span class="sxs-lookup"><span data-stu-id="2cb29-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="2cb29-137">Il valore più utile per diagnosticare i problemi di prestazioni è **SPRequestDuration**, che visualizza il tempo impiegato dalla richiesta sul server per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2cb29-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="2cb29-138">Ciò consente di determinare se la richiesta è molto pesante e richiede un utilizzo intensivo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2cb29-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="2cb29-139">Questa è la migliore conoscenza disponibile relativa all'attività del server per visualizzare la pagina.</span><span class="sxs-lookup"><span data-stu-id="2cb29-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="2cb29-140">Per visualizzare le informazioni di intestazione della risposta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cb29-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="2cb29-141">Verificare di avere installato gli strumenti F12.</span><span class="sxs-lookup"><span data-stu-id="2cb29-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="2cb29-142">Per ulteriori informazioni sul download e l'installazione di questi strumenti, vedere [Novità degli strumenti F12.](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="2cb29-142">For more information on downloading and installing these tools, see [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span></span>

2. <span data-ttu-id="2cb29-143">Negli strumenti F12,nella scheda **Rete**, premere il pulsante verde di riproduzione per caricare la pagina.</span><span class="sxs-lookup"><span data-stu-id="2cb29-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="2cb29-144">Fare clic sui file .aspx restituiti dagli strumenti, quindi fare clic su **DETTAGLI**.</span><span class="sxs-lookup"><span data-stu-id="2cb29-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Mostra i dettagli dell'intestazione della risposta](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="2cb29-146">Fare clic su **Intestazioni di risposta**.</span><span class="sxs-lookup"><span data-stu-id="2cb29-146">Click **Response headers**.</span></span>

    ![Diagramma che mostra l'URL dell'intestazione della risposta](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="2cb29-148">Qual è la causa dei problemi delle prestazioni in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="2cb29-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="2cb29-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="2cb29-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="2cb29-150">Nell'articolo [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) viene illustrato un esempio dell'utilizzo del valore SPRequestDuration per determinare che la navigazione strutturale complicata causava che la pagina richiedeva molto tempo per l'elaborazione sul server.</span><span class="sxs-lookup"><span data-stu-id="2cb29-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="2cb29-151">Adottando un valore per un sito di base (senza personalizzazione), è possibile determinare se un determinato file richieda molto tempo per il caricamento.</span><span class="sxs-lookup"><span data-stu-id="2cb29-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="2cb29-152">Nell'esempio utilizzato in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) è il file .aspx principale.</span><span class="sxs-lookup"><span data-stu-id="2cb29-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="2cb29-153">Tale file contiene la maggior parte del codice ASP.NET che viene eseguito per il caricamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="2cb29-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="2cb29-154">A seconda del modello di sito utilizzato, potrebbe trattarsi di start.aspx, home.aspx, default.aspx o di un altro nome se si personalizza la home page.</span><span class="sxs-lookup"><span data-stu-id="2cb29-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="2cb29-155">Se questo numero è notevolmente superiore al sito di base, è molto probabile che sia in corso qualcosa di complesso nella pagina che causa problemi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2cb29-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="2cb29-p109">Dopo aver chiarito che si tratta di un problema specifico del sito, il metodo consigliato per individuare la causa della riduzione delle prestazioni è l'eliminazione di tutte le possibili cause, come le personalizzazioni della pagina, per poi riaggiungerle al sito una alla volta. Dopo aver rimosso sufficienti personalizzazioni soddisfacenti della pagina, sarà quindi possibile riaggiungere le personalizzazioni specifiche una alla volta.</span><span class="sxs-lookup"><span data-stu-id="2cb29-p109">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one. Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="2cb29-158">Ad esempio, se si dispone di una struttura di spostamento molto complessa provare a modificare tale struttura per non visualizzare siti secondari, quindi controllare gli strumenti di sviluppo per vedere se ci sono differenze.</span><span class="sxs-lookup"><span data-stu-id="2cb29-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="2cb29-159">In alternativa, se si dispone di una grande quantità di contenuti di aggiornamenti cumulativi provare a rimuoverli dalla pagina e vedere se si ottengono miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="2cb29-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="2cb29-160">Se si eliminano tutte le possibili cause e si aggiungono nuovamente una alla volta, è possibile identificare facilmente quali funzionalità sono il problema principale, per poi lavorare a una soluzione.</span><span class="sxs-lookup"><span data-stu-id="2cb29-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>