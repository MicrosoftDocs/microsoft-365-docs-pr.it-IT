---
title: ID evento e codici di errore di Microsoft Defender AV
description: Cercare le cause e le soluzioni per Antivirus Microsoft Defender e gli errori degli eventi
keywords: evento, codice di errore, siem, registrazione, risoluzione dei problemi, wef, inoltro di eventi di Windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275349"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="d11b2-104">Esaminare i log eventi e i codici di errore per risolvere i problemi relativi a Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d11b2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d11b2-105">**Applies to:**</span></span>

- [<span data-ttu-id="d11b2-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d11b2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d11b2-107">Se si verifica un problema con Antivirus Microsoft Defender, è possibile cercare nelle tabelle di questo argomento un problema corrispondente e una soluzione potenziale.</span><span class="sxs-lookup"><span data-stu-id="d11b2-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="d11b2-108">L'elenco delle tabelle:</span><span class="sxs-lookup"><span data-stu-id="d11b2-108">The tables list:</span></span>

- <span data-ttu-id="d11b2-109">[Antivirus Microsoft Defender ID evento](#windows-defender-av-ids) (si applicano sia a Windows 10 che Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="d11b2-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="d11b2-110">Antivirus Microsoft Defender di errore del client</span><span class="sxs-lookup"><span data-stu-id="d11b2-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="d11b2-111">Codici Antivirus Microsoft Defender client interni (utilizzati da Microsoft durante lo sviluppo e il testing)</span><span class="sxs-lookup"><span data-stu-id="d11b2-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="d11b2-112">Puoi anche visitare il sito Web demo di Microsoft Defender for Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che le funzionalità seguenti funzionino:</span><span class="sxs-lookup"><span data-stu-id="d11b2-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="d11b2-113">Protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="d11b2-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="d11b2-114">Apprendimento rapido (incluso Blocco a prima vista)</span><span class="sxs-lookup"><span data-stu-id="d11b2-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="d11b2-115">Blocco di applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="d11b2-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="d11b2-116">Antivirus Microsoft Defender ID evento</span><span class="sxs-lookup"><span data-stu-id="d11b2-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="d11b2-117">Antivirus Microsoft Defender registra gli ID evento nel Windows eventi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="d11b2-118">È possibile visualizzare direttamente il registro eventi oppure, se si dispone di uno strumento siem (Security Information and Event Management) di terze parti, è inoltre possibile utilizzare gli ID evento [client Antivirus Microsoft Defender](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) per esaminare eventi ed errori specifici dagli endpoint.</span><span class="sxs-lookup"><span data-stu-id="d11b2-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="d11b2-119">Nella tabella di questa sezione sono elencati gli ID Antivirus Microsoft Defender eventi principali e, se possibile, vengono fornite soluzioni suggerite per correggere o risolvere l'errore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="d11b2-120">Per visualizzare un Antivirus Microsoft Defender evento</span><span class="sxs-lookup"><span data-stu-id="d11b2-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="d11b2-121">Aprire **visualizzatore eventi**.</span><span class="sxs-lookup"><span data-stu-id="d11b2-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="d11b2-122">Nell'albero della console espandere **Registri applicazioni** e servizi , **quindi Microsoft**, quindi **Windows**, **quindi Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="d11b2-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="d11b2-123">Fare doppio clic su **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="d11b2-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="d11b2-124">Nel riquadro dei dettagli, visualizzare l'elenco dei singoli eventi per trovare l'evento.</span><span class="sxs-lookup"><span data-stu-id="d11b2-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="d11b2-125">Fare clic sull'evento per visualizzare dettagli specifici su un evento nel riquadro inferiore, nelle **schede Generale** **e** Dettagli.</span><span class="sxs-lookup"><span data-stu-id="d11b2-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="d11b2-126">ID evento: 1000</span><span class="sxs-lookup"><span data-stu-id="d11b2-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-127">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="d11b2-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-129">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-129">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-130">
<b>Analisi antimalware avviata. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="d11b2-131">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d11b2-132">
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-133">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-134">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-135">Antimalware</span></span></li>
</ul><span data-ttu-id="d11b2-136">
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-137">Analisi completa</span><span class="sxs-lookup"><span data-stu-id="d11b2-137">Full scan</span></span></li>
<li><span data-ttu-id="d11b2-138">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="d11b2-138">Quick scan</span></span></li>
<li><span data-ttu-id="d11b2-139">Analisi del cliente</span><span class="sxs-lookup"><span data-stu-id="d11b2-139">Customer scan</span></span></li>
</ul><span data-ttu-id="d11b2-140">
</dt>
<dt>Risorse analisi: &lt; Risorse (ad esempio file/directory/BHO) &gt; analizzate.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; Utente &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-141">ID evento: 1001</span><span class="sxs-lookup"><span data-stu-id="d11b2-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-142">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-144">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-144">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-145">
<b>Analisi antimalware completata.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-146">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d11b2-147">
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-148">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-149">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-150">Antimalware</span></span></li>
</ul><span data-ttu-id="d11b2-151">
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-152">Analisi completa</span><span class="sxs-lookup"><span data-stu-id="d11b2-152">Full scan</span></span></li>
<li><span data-ttu-id="d11b2-153">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="d11b2-153">Quick scan</span></span></li>
<li><span data-ttu-id="d11b2-154">Analisi del cliente</span><span class="sxs-lookup"><span data-stu-id="d11b2-154">Customer scan</span></span></li>
</ul><span data-ttu-id="d11b2-155">
</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Scan Time: &lt; durata di &gt; un'analisi.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-156">ID evento: 1002</span><span class="sxs-lookup"><span data-stu-id="d11b2-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-157">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-159">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-159">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-160">
<b>Un'analisi antimalware è stata interrotta prima del termine. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-161">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d11b2-162">
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-163">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-164">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-165">Antimalware</span></span></li>
</ul><span data-ttu-id="d11b2-166">
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-167">Analisi completa</span><span class="sxs-lookup"><span data-stu-id="d11b2-167">Full scan</span></span></li>
<li><span data-ttu-id="d11b2-168">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="d11b2-168">Quick scan</span></span></li>
<li><span data-ttu-id="d11b2-169">Analisi del cliente</span><span class="sxs-lookup"><span data-stu-id="d11b2-169">Customer scan</span></span></li>
</ul><span data-ttu-id="d11b2-170">
</dt>
<dt>Utente: &lt; Dominio &gt; &amp; lt; User &gt; </dt>
<dt>Scan Time: &lt; durata di &gt; un'analisi.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-171">ID evento: 1003</span><span class="sxs-lookup"><span data-stu-id="d11b2-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-172">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-174">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-174">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-175">
<b>Un'analisi antimalware è stata sospesa. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-176">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d11b2-177">
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-178">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-179">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-180">Antimalware</span></span></li>
</ul><span data-ttu-id="d11b2-181">
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-182">Analisi completa</span><span class="sxs-lookup"><span data-stu-id="d11b2-182">Full scan</span></span></li>
<li><span data-ttu-id="d11b2-183">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="d11b2-183">Quick scan</span></span></li>
<li><span data-ttu-id="d11b2-184">Analisi del cliente</span><span class="sxs-lookup"><span data-stu-id="d11b2-184">Customer scan</span></span></li>
</ul><span data-ttu-id="d11b2-185">
</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; Utente&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-186">ID evento: 1004</span><span class="sxs-lookup"><span data-stu-id="d11b2-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-187">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-189">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-189">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-190">
<b>È stata ripresa un'analisi antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-191">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d11b2-192">
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-193">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-194">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-195">Antimalware</span></span></li>
</ul><span data-ttu-id="d11b2-196">
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-197">Analisi completa</span><span class="sxs-lookup"><span data-stu-id="d11b2-197">Full scan</span></span></li>
<li><span data-ttu-id="d11b2-198">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="d11b2-198">Quick scan</span></span></li>
<li><span data-ttu-id="d11b2-199">Analisi del cliente</span><span class="sxs-lookup"><span data-stu-id="d11b2-199">Customer scan</span></span></li>
</ul><span data-ttu-id="d11b2-200">
</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; Utente&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-201">ID evento: 1005</span><span class="sxs-lookup"><span data-stu-id="d11b2-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-202">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-204">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-204">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-205">
<b>Analisi antimalware non riuscita. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-206">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="d11b2-207">
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-208">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-209">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-210">Antimalware</span></span></li>
</ul><span data-ttu-id="d11b2-211">
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-212">Analisi completa</span><span class="sxs-lookup"><span data-stu-id="d11b2-212">Full scan</span></span></li>
<li><span data-ttu-id="d11b2-213">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="d11b2-213">Quick scan</span></span></li>
<li><span data-ttu-id="d11b2-214">Analisi del cliente</span><span class="sxs-lookup"><span data-stu-id="d11b2-214">Customer scan</span></span></li>
</ul><span data-ttu-id="d11b2-215">
</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-216">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-217">Il client antivirus ha rilevato un errore e l'analisi corrente è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="d11b2-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="d11b2-218">L'analisi potrebbe non riuscire a causa di un problema sul lato client.</span><span class="sxs-lookup"><span data-stu-id="d11b2-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="d11b2-219">Questo record di evento include l'ID analisi, il tipo di analisi (Antivirus Microsoft Defender, antispyware, antimalware), i parametri di analisi, l'utente che ha avviato l'analisi, il codice di errore e una descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="d11b2-220">Per risolvere i problemi relativi a questo evento:</span><span class="sxs-lookup"><span data-stu-id="d11b2-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d11b2-221">Eseguire di nuovo l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="d11b2-222">Se si verifica un errore nello stesso modo, accedere al <b></b> sito del Supporto <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Tecnico Microsoft,</a>immettere il numero di errore nella casella Cerca per cercare il codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="d11b2-223">Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-224">ID evento: 1006</span><span class="sxs-lookup"><span data-stu-id="d11b2-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-225">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-227">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-227">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-228">
<b>Il motore antimalware ha rilevato malware o altro software potenzialmente indesiderato. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-229">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-230">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-231">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-232">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-232">Low</span></span></li>
<li><span data-ttu-id="d11b2-233">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-233">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-234">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-234">High</span></span></li>
<li><span data-ttu-id="d11b2-235">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-235">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-236">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-237">Unknown</span><span class="sxs-lookup"><span data-stu-id="d11b2-237">Unknown</span></span></li>
<li><span data-ttu-id="d11b2-238">Computer locale</span><span class="sxs-lookup"><span data-stu-id="d11b2-238">Local computer</span></span></li>
<li><span data-ttu-id="d11b2-239">Condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-239">Network share</span></span></li>
<li><span data-ttu-id="d11b2-240">Internet</span><span class="sxs-lookup"><span data-stu-id="d11b2-240">Internet</span></span></li>
<li><span data-ttu-id="d11b2-241">Traffico in ingresso</span><span class="sxs-lookup"><span data-stu-id="d11b2-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="d11b2-242">Traffico in uscita</span><span class="sxs-lookup"><span data-stu-id="d11b2-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d11b2-243">
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-244">Euristica</span><span class="sxs-lookup"><span data-stu-id="d11b2-244">Heuristics</span></span></li>
<li><span data-ttu-id="d11b2-245">Generale</span><span class="sxs-lookup"><span data-stu-id="d11b2-245">Generic</span></span></li>
<li><span data-ttu-id="d11b2-246">Concrete</span><span class="sxs-lookup"><span data-stu-id="d11b2-246">Concrete</span></span></li>
<li><span data-ttu-id="d11b2-247">Firma dinamica</span><span class="sxs-lookup"><span data-stu-id="d11b2-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d11b2-248">
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d11b2-249">Utente: avviato dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-249">User: user initiated</span></span></li>
<li><span data-ttu-id="d11b2-250">Sistema: sistema avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-250">System: system initiated</span></span></li>
<li><span data-ttu-id="d11b2-251">Tempo reale: componente in tempo reale avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d11b2-252">IOAV: download di Internet Outlook express allegati avviati</span><span class="sxs-lookup"><span data-stu-id="d11b2-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d11b2-253">NIS: sistema di ispezione della rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d11b2-254">IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</span><span class="sxs-lookup"><span data-stu-id="d11b2-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d11b2-255">Antimalware di avvio anticipato (ELAM).</span><span class="sxs-lookup"><span data-stu-id="d11b2-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d11b2-256">Ciò include il malware rilevato dalla sequenza di avvio</span><span class="sxs-lookup"><span data-stu-id="d11b2-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d11b2-257">Attestazione remota</span><span class="sxs-lookup"><span data-stu-id="d11b2-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="d11b2-258">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="d11b2-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d11b2-259">Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.</span><span class="sxs-lookup"><span data-stu-id="d11b2-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d11b2-260">Stato controllo </dt> 
<dt>dell'account utente: &lt; &gt; Stato</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-261">ID evento: 1007</span><span class="sxs-lookup"><span data-stu-id="d11b2-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-262">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-264">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-264">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-265">
<b>La piattaforma antimalware ha eseguito un'azione per proteggere il sistema da malware o altro software potenzialmente indesiderato. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-266">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-267">Antivirus Microsoft Defender ha intrapreso azioni per proteggere il computer da malware o altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="d11b2-268">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-269">
<dt>Utente: &lt; Dominio &gt; \& lt; Nome &gt; </dt>
<dt>utente: &lt; ID nome minaccia: &gt; </dt>
<dt> &lt; Gravità ID &gt; </dt> 
<dt> minaccia: &lt; Gravità, ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-270">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-270">Low</span></span></li>
<li><span data-ttu-id="d11b2-271">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-271">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-272">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-272">High</span></span></li>
<li><span data-ttu-id="d11b2-273">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-273">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-274">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt> Azione: &lt; Azione , ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-275">Clean: la risorsa è stata pulita</span><span class="sxs-lookup"><span data-stu-id="d11b2-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d11b2-276">Quarantena: la risorsa è stata messi in quarantena</span><span class="sxs-lookup"><span data-stu-id="d11b2-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d11b2-277">Rimuovi: la risorsa è stata eliminata</span><span class="sxs-lookup"><span data-stu-id="d11b2-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d11b2-278">Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</span><span class="sxs-lookup"><span data-stu-id="d11b2-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d11b2-279">Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d11b2-280">Nessuna azione: nessuna azione</span><span class="sxs-lookup"><span data-stu-id="d11b2-280">No action: No action</span></span></li>
<li><span data-ttu-id="d11b2-281">Blocca: l'esecuzione della risorsa è stata bloccata</span><span class="sxs-lookup"><span data-stu-id="d11b2-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d11b2-282">
</dt>
<dt>Stato: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-283">ID evento: 1008</span><span class="sxs-lookup"><span data-stu-id="d11b2-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-284">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-286">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-286">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-287">
<b>La piattaforma antimalware ha tentato di eseguire un'azione per proteggere il sistema da malware o altro software potenzialmente indesiderato, ma l'azione non è riuscita.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-288">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-289">Antivirus Microsoft Defender si è verificato un errore durante l'azione su malware o altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="d11b2-290">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-291">
<dt>Utente: &lt; Dominio &gt; \& lt; Nome &gt; </dt>
<dt>utente: &lt; ID nome minaccia: &gt; </dt>
<dt> &lt; Gravità ID &gt; </dt> 
<dt> minaccia: &lt; Gravità, ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-292">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-292">Low</span></span></li>
<li><span data-ttu-id="d11b2-293">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-293">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-294">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-294">High</span></span></li>
<li><span data-ttu-id="d11b2-295">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-295">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-296">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Azione: &lt; &gt; Azione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-297">Clean: la risorsa è stata pulita</span><span class="sxs-lookup"><span data-stu-id="d11b2-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d11b2-298">Quarantena: la risorsa è stata messi in quarantena</span><span class="sxs-lookup"><span data-stu-id="d11b2-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d11b2-299">Rimuovi: la risorsa è stata eliminata</span><span class="sxs-lookup"><span data-stu-id="d11b2-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d11b2-300">Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</span><span class="sxs-lookup"><span data-stu-id="d11b2-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d11b2-301">Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d11b2-302">Nessuna azione: nessuna azione</span><span class="sxs-lookup"><span data-stu-id="d11b2-302">No action: No action</span></span></li>
<li><span data-ttu-id="d11b2-303">Blocca: l'esecuzione della risorsa è stata bloccata</span><span class="sxs-lookup"><span data-stu-id="d11b2-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d11b2-304">
</dt>
<dt>Codice errore: &lt; Codice di errore &gt; Codice di risultato associato allo stato della minaccia. Valori HRESULT standard. </dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; errore Descrizione dell'errore.</dt> 
<dt>Stato: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-305">ID evento: 1009</span><span class="sxs-lookup"><span data-stu-id="d11b2-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-306">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-308">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-308">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-309">
<b>La piattaforma antimalware ha ripristinato un elemento dalla quarantena. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-310">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-311">Antivirus Microsoft Defender ha ripristinato un elemento dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="d11b2-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="d11b2-312">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-313">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-314">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-314">Low</span></span></li>
<li><span data-ttu-id="d11b2-315">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-315">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-316">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-316">High</span></span></li>
<li><span data-ttu-id="d11b2-317">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-317">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-318">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; Versione &gt; </dt>
<dt>firma utente: &lt; versione definizione &gt; </dt>Versione
<dt>motore: Antimalware Engine &lt; versione &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-319">ID evento: 1010</span><span class="sxs-lookup"><span data-stu-id="d11b2-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-320">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-322">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-322">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-323">
<b>La piattaforma antimalware non è in grado di ripristinare un elemento dalla quarantena. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-324">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-325">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di ripristinare un elemento dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="d11b2-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="d11b2-326">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-327">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-328">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-328">Low</span></span></li>
<li><span data-ttu-id="d11b2-329">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-329">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-330">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-330">High</span></span></li>
<li><span data-ttu-id="d11b2-331">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-331">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-332">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard. </dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-333">ID evento: 1011</span><span class="sxs-lookup"><span data-stu-id="d11b2-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-334">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-336">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-336">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-337">
<b>La piattaforma antimalware ha eliminato un elemento dalla quarantena. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-338">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-339">Antivirus Microsoft Defender ha eliminato un elemento dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="d11b2-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="d11b2-340">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-341">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-342">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-342">Low</span></span></li>
<li><span data-ttu-id="d11b2-343">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-343">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-344">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-344">High</span></span></li>
<li><span data-ttu-id="d11b2-345">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-345">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-346">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; Versione &gt; </dt>
<dt>firma utente: &lt; versione definizione &gt; </dt>Versione
<dt>motore: Antimalware Engine &lt; versione &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-347">ID evento: 1012</span><span class="sxs-lookup"><span data-stu-id="d11b2-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-348">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-350">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-350">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-351">
<b>La piattaforma antimalware non è stata in grado di eliminare un elemento dalla quarantena.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-352">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-353">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di eliminare un elemento dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="d11b2-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="d11b2-354">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-355">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-356">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-356">Low</span></span></li>
<li><span data-ttu-id="d11b2-357">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-357">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-358">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-358">High</span></span></li>
<li><span data-ttu-id="d11b2-359">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-359">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-360">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard. </dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-361">ID evento: 1013</span><span class="sxs-lookup"><span data-stu-id="d11b2-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-362">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-364">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-364">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-365">
<b>La piattaforma antimalware ha eliminato la cronologia del malware e di altro software potenzialmente indesiderato.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-366">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-367">Antivirus Microsoft Defender ha rimosso la cronologia del malware e di altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="d11b2-368">
<dt>Time: ora in cui si è verificato l'evento, ad esempio quando la cronologia viene eliminata. Questo parametro non viene utilizzato negli eventi di minaccia in modo da non creare confusione riguardo al tempo di correzione o all'infezione. Per questi, li chiamiamo in modo specifico come Tempo azione o Tempo di rilevamento.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; Utente &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-369">ID evento: 1014</span><span class="sxs-lookup"><span data-stu-id="d11b2-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-370">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-372">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-373">La piattaforma antimalware non è in grado di eliminare la cronologia del malware e di altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-374">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-375">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di rimuovere la cronologia del malware e di altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="d11b2-376">
<dt>Time: ora in cui si è verificato l'evento, ad esempio quando la cronologia viene eliminata. Questo parametro non viene utilizzato negli eventi di minaccia in modo da non creare confusione riguardo al tempo di correzione o all'infezione. Per questi, li chiamiamo in modo specifico come Tempo azione o Tempo di rilevamento.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard. </dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; errore Descrizione dell'errore.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-377">ID evento: 1015</span><span class="sxs-lookup"><span data-stu-id="d11b2-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-378">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-380">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-380">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-381">
<b>La piattaforma antimalware ha rilevato comportamenti sospetti.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-382">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-383">Antivirus Microsoft Defender ha rilevato un comportamento sospetto.</span><span class="sxs-lookup"><span data-stu-id="d11b2-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="d11b2-384">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-385">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-386">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-386">Low</span></span></li>
<li><span data-ttu-id="d11b2-387">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-387">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-388">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-388">High</span></span></li>
<li><span data-ttu-id="d11b2-389">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-389">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-390">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-391">Unknown</span><span class="sxs-lookup"><span data-stu-id="d11b2-391">Unknown</span></span></li>
<li><span data-ttu-id="d11b2-392">Computer locale</span><span class="sxs-lookup"><span data-stu-id="d11b2-392">Local computer</span></span></li>
<li><span data-ttu-id="d11b2-393">Condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-393">Network share</span></span></li>
<li><span data-ttu-id="d11b2-394">Internet</span><span class="sxs-lookup"><span data-stu-id="d11b2-394">Internet</span></span></li>
<li><span data-ttu-id="d11b2-395">Traffico in ingresso</span><span class="sxs-lookup"><span data-stu-id="d11b2-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="d11b2-396">Traffico in uscita</span><span class="sxs-lookup"><span data-stu-id="d11b2-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d11b2-397">
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-398">Euristica</span><span class="sxs-lookup"><span data-stu-id="d11b2-398">Heuristics</span></span></li>
<li><span data-ttu-id="d11b2-399">Generale</span><span class="sxs-lookup"><span data-stu-id="d11b2-399">Generic</span></span></li>
<li><span data-ttu-id="d11b2-400">Concrete</span><span class="sxs-lookup"><span data-stu-id="d11b2-400">Concrete</span></span></li>
<li><span data-ttu-id="d11b2-401">Firma dinamica</span><span class="sxs-lookup"><span data-stu-id="d11b2-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d11b2-402">
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d11b2-403">Utente: avviato dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-403">User: user initiated</span></span></li>
<li><span data-ttu-id="d11b2-404">Sistema: sistema avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-404">System: system initiated</span></span></li>
<li><span data-ttu-id="d11b2-405">Tempo reale: componente in tempo reale avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d11b2-406">IOAV: download di Internet Outlook express allegati avviati</span><span class="sxs-lookup"><span data-stu-id="d11b2-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d11b2-407">NIS: sistema di ispezione della rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d11b2-408">IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</span><span class="sxs-lookup"><span data-stu-id="d11b2-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d11b2-409">Antimalware di avvio anticipato (ELAM).</span><span class="sxs-lookup"><span data-stu-id="d11b2-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d11b2-410">Ciò include il malware rilevato dalla sequenza di avvio</span><span class="sxs-lookup"><span data-stu-id="d11b2-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d11b2-411">Attestazione remota</span><span class="sxs-lookup"><span data-stu-id="d11b2-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="d11b2-412">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="d11b2-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d11b2-413">Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.</span><span class="sxs-lookup"><span data-stu-id="d11b2-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d11b2-414">Stato controllo </dt> 
<dt>dell'account utente: &lt; &gt; Stato</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt>
<dt>Signature ID: Enumeration matching severity.</dt> 
<dt>Versione firma: &lt; Versione &gt; definizione</dt>
<dt>Versione motore: &lt; Antimalware Engine &gt; versione</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: File name Name Name &lt; of the &gt; file.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-415">ID evento: 1116</span><span class="sxs-lookup"><span data-stu-id="d11b2-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-416">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-418">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-418">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-419">
<b>La piattaforma antimalware ha rilevato malware o altro software potenzialmente indesiderato. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-420">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-421">Antivirus Microsoft Defender ha rilevato malware o altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="d11b2-422">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-423">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-424">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-424">Low</span></span></li>
<li><span data-ttu-id="d11b2-425">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-425">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-426">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-426">High</span></span></li>
<li><span data-ttu-id="d11b2-427">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-427">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-428">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-429">Unknown</span><span class="sxs-lookup"><span data-stu-id="d11b2-429">Unknown</span></span></li>
<li><span data-ttu-id="d11b2-430">Computer locale</span><span class="sxs-lookup"><span data-stu-id="d11b2-430">Local computer</span></span></li>
<li><span data-ttu-id="d11b2-431">Condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-431">Network share</span></span></li>
<li><span data-ttu-id="d11b2-432">Internet</span><span class="sxs-lookup"><span data-stu-id="d11b2-432">Internet</span></span></li>
<li><span data-ttu-id="d11b2-433">Traffico in ingresso</span><span class="sxs-lookup"><span data-stu-id="d11b2-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="d11b2-434">Traffico in uscita</span><span class="sxs-lookup"><span data-stu-id="d11b2-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d11b2-435">
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-436">Euristica</span><span class="sxs-lookup"><span data-stu-id="d11b2-436">Heuristics</span></span></li>
<li><span data-ttu-id="d11b2-437">Generale</span><span class="sxs-lookup"><span data-stu-id="d11b2-437">Generic</span></span></li>
<li><span data-ttu-id="d11b2-438">Concrete</span><span class="sxs-lookup"><span data-stu-id="d11b2-438">Concrete</span></span></li>
<li><span data-ttu-id="d11b2-439">Firma dinamica</span><span class="sxs-lookup"><span data-stu-id="d11b2-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d11b2-440">
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d11b2-441">Utente: avviato dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-441">User: user initiated</span></span></li>
<li><span data-ttu-id="d11b2-442">Sistema: sistema avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-442">System: system initiated</span></span></li>
<li><span data-ttu-id="d11b2-443">Tempo reale: componente in tempo reale avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d11b2-444">IOAV: download di Internet Outlook express allegati avviati</span><span class="sxs-lookup"><span data-stu-id="d11b2-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d11b2-445">NIS: sistema di ispezione della rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d11b2-446">IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</span><span class="sxs-lookup"><span data-stu-id="d11b2-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d11b2-447">Antimalware di avvio anticipato (ELAM).</span><span class="sxs-lookup"><span data-stu-id="d11b2-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d11b2-448">Ciò include il malware rilevato dalla sequenza di avvio</span><span class="sxs-lookup"><span data-stu-id="d11b2-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d11b2-449">Attestazione remota</span><span class="sxs-lookup"><span data-stu-id="d11b2-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="d11b2-450">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="d11b2-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d11b2-451">Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.</span><span class="sxs-lookup"><span data-stu-id="d11b2-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d11b2-452">Utente </dt> 
<dt>UAC: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-453">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-454">Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d11b2-454">No action is required.</span></span> <span data-ttu-id="d11b2-455">Antivirus Microsoft Defender possibile sospendere ed eseguire azioni di routine su questa minaccia.</span><span class="sxs-lookup"><span data-stu-id="d11b2-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="d11b2-456">Se si desidera rimuovere manualmente la minaccia, nell'interfaccia Antivirus Microsoft Defender fare clic su <b>Pulisci computer</b>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-457">ID evento: 1117</span><span class="sxs-lookup"><span data-stu-id="d11b2-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-458">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-460">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-460">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-461">
<b>La piattaforma antimalware ha eseguito un'azione per proteggere il sistema da malware o altro software potenzialmente indesiderato. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-462">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-463">Antivirus Microsoft Defender ha intrapreso azioni per proteggere il computer da malware o altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="d11b2-464">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-465">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-466">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-466">Low</span></span></li>
<li><span data-ttu-id="d11b2-467">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-467">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-468">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-468">High</span></span></li>
<li><span data-ttu-id="d11b2-469">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-469">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-470">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-471">Unknown</span><span class="sxs-lookup"><span data-stu-id="d11b2-471">Unknown</span></span></li>
<li><span data-ttu-id="d11b2-472">Computer locale</span><span class="sxs-lookup"><span data-stu-id="d11b2-472">Local computer</span></span></li>
<li><span data-ttu-id="d11b2-473">Condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-473">Network share</span></span></li>
<li><span data-ttu-id="d11b2-474">Internet</span><span class="sxs-lookup"><span data-stu-id="d11b2-474">Internet</span></span></li>
<li><span data-ttu-id="d11b2-475">Traffico in ingresso</span><span class="sxs-lookup"><span data-stu-id="d11b2-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="d11b2-476">Traffico in uscita</span><span class="sxs-lookup"><span data-stu-id="d11b2-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d11b2-477">
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-478">Euristica</span><span class="sxs-lookup"><span data-stu-id="d11b2-478">Heuristics</span></span></li>
<li><span data-ttu-id="d11b2-479">Generale</span><span class="sxs-lookup"><span data-stu-id="d11b2-479">Generic</span></span></li>
<li><span data-ttu-id="d11b2-480">Concrete</span><span class="sxs-lookup"><span data-stu-id="d11b2-480">Concrete</span></span></li>
<li><span data-ttu-id="d11b2-481">Firma dinamica</span><span class="sxs-lookup"><span data-stu-id="d11b2-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d11b2-482">
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d11b2-483">Utente: avviato dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-483">User: user initiated</span></span></li>
<li><span data-ttu-id="d11b2-484">Sistema: sistema avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-484">System: system initiated</span></span></li>
<li><span data-ttu-id="d11b2-485">Tempo reale: componente in tempo reale avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d11b2-486">IOAV: download di Internet Outlook express allegati avviati</span><span class="sxs-lookup"><span data-stu-id="d11b2-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d11b2-487">NIS: sistema di ispezione della rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d11b2-488">IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</span><span class="sxs-lookup"><span data-stu-id="d11b2-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d11b2-489">Antimalware di avvio anticipato (ELAM).</span><span class="sxs-lookup"><span data-stu-id="d11b2-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d11b2-490">Ciò include il malware rilevato dalla sequenza di avvio</span><span class="sxs-lookup"><span data-stu-id="d11b2-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d11b2-491">Attestazione remota</span><span class="sxs-lookup"><span data-stu-id="d11b2-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="d11b2-492">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="d11b2-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d11b2-493">Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.</span><span class="sxs-lookup"><span data-stu-id="d11b2-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d11b2-494">Utente </dt> 
<dt>UAC: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt> 
<dt> Action: &lt; Action , ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-495">Clean: la risorsa è stata pulita</span><span class="sxs-lookup"><span data-stu-id="d11b2-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d11b2-496">Quarantena: la risorsa è stata messi in quarantena</span><span class="sxs-lookup"><span data-stu-id="d11b2-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d11b2-497">Rimuovi: la risorsa è stata eliminata</span><span class="sxs-lookup"><span data-stu-id="d11b2-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d11b2-498">Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</span><span class="sxs-lookup"><span data-stu-id="d11b2-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d11b2-499">Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d11b2-500">Nessuna azione: nessuna azione</span><span class="sxs-lookup"><span data-stu-id="d11b2-500">No action: No action</span></span></li>
<li><span data-ttu-id="d11b2-501">Blocca: l'esecuzione della risorsa è stata bloccata</span><span class="sxs-lookup"><span data-stu-id="d11b2-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d11b2-502">
</dt>
<dt>Stato azione: &lt; Descrizione delle &gt; azioni aggiuntive</dt>
<dt>Codice di errore: Codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; del</dt>motore versione
<dt>definizione: &lt; versione Antimalware Engine &gt; </dt> NOTA: ogni volta che Antivirus Microsoft Defender, Microsoft Security Essentials, Lo strumento di rimozione di software dannoso o System Center Endpoint Protection rileva un malware, ripristina le impostazioni di sistema e i servizi seguenti che il malware potrebbe essere cambiato:</span><span class="sxs-lookup"><span data-stu-id="d11b2-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="d11b2-503">Impostazione predefinita di Internet Explorer o Microsoft Edge predefinita</span><span class="sxs-lookup"><span data-stu-id="d11b2-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="d11b2-504">Impostazioni di Controllo di accesso utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="d11b2-505">Impostazioni di Chrome</span><span class="sxs-lookup"><span data-stu-id="d11b2-505">Chrome settings</span></span></li>
<li><span data-ttu-id="d11b2-506">Dati di controllo di avvio</span><span class="sxs-lookup"><span data-stu-id="d11b2-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="d11b2-507">Impostazioni del Registro di sistema di Regedit e Task Manager</span><span class="sxs-lookup"><span data-stu-id="d11b2-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="d11b2-508">Windows Aggiornamento, Servizio trasferimento intelligente in background e Servizio di chiamata di procedura remota</span><span class="sxs-lookup"><span data-stu-id="d11b2-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="d11b2-509">Windows File del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d11b2-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="d11b2-510">Il contesto precedente si applica alle versioni client e server seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="d11b2-511">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d11b2-511">Operating system</span></span></th>
<th><span data-ttu-id="d11b2-512">Versione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d11b2-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-513">Sistema operativo client</span><span class="sxs-lookup"><span data-stu-id="d11b2-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="d11b2-514">Windows Vista (Service Pack 1 o Service Pack 2), Windows 7 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="d11b2-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-515">Sistema operativo server</span><span class="sxs-lookup"><span data-stu-id="d11b2-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="d11b2-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 e Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d11b2-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-517">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-518">Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d11b2-518">No action is necessary.</span></span> <span data-ttu-id="d11b2-519">Antivirus Microsoft Defender rimosso o messo in quarantena una minaccia.</span><span class="sxs-lookup"><span data-stu-id="d11b2-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-520">ID evento: 1118</span><span class="sxs-lookup"><span data-stu-id="d11b2-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-521">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-523">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-523">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-524">
<b>La piattaforma antimalware ha tentato di eseguire un'azione per proteggere il sistema da malware o altro software potenzialmente indesiderato, ma l'azione non è riuscita. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-525">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-526">Antivirus Microsoft Defender si è verificato un errore non critico quando si esegue un'azione su malware o altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="d11b2-527">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-528">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-529">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-529">Low</span></span></li>
<li><span data-ttu-id="d11b2-530">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-530">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-531">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-531">High</span></span></li>
<li><span data-ttu-id="d11b2-532">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-532">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-533">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-534">Unknown</span><span class="sxs-lookup"><span data-stu-id="d11b2-534">Unknown</span></span></li>
<li><span data-ttu-id="d11b2-535">Computer locale</span><span class="sxs-lookup"><span data-stu-id="d11b2-535">Local computer</span></span></li>
<li><span data-ttu-id="d11b2-536">Condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-536">Network share</span></span></li>
<li><span data-ttu-id="d11b2-537">Internet</span><span class="sxs-lookup"><span data-stu-id="d11b2-537">Internet</span></span></li>
<li><span data-ttu-id="d11b2-538">Traffico in ingresso</span><span class="sxs-lookup"><span data-stu-id="d11b2-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="d11b2-539">Traffico in uscita</span><span class="sxs-lookup"><span data-stu-id="d11b2-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d11b2-540">
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-541">Euristica</span><span class="sxs-lookup"><span data-stu-id="d11b2-541">Heuristics</span></span></li>
<li><span data-ttu-id="d11b2-542">Generale</span><span class="sxs-lookup"><span data-stu-id="d11b2-542">Generic</span></span></li>
<li><span data-ttu-id="d11b2-543">Concrete</span><span class="sxs-lookup"><span data-stu-id="d11b2-543">Concrete</span></span></li>
<li><span data-ttu-id="d11b2-544">Firma dinamica</span><span class="sxs-lookup"><span data-stu-id="d11b2-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d11b2-545">
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d11b2-546">Utente: avviato dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-546">User: user initiated</span></span></li>
<li><span data-ttu-id="d11b2-547">Sistema: sistema avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-547">System: system initiated</span></span></li>
<li><span data-ttu-id="d11b2-548">Tempo reale: componente in tempo reale avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d11b2-549">IOAV: download di Internet Outlook express allegati avviati</span><span class="sxs-lookup"><span data-stu-id="d11b2-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d11b2-550">NIS: sistema di ispezione della rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d11b2-551">IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</span><span class="sxs-lookup"><span data-stu-id="d11b2-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d11b2-552">Antimalware di avvio anticipato (ELAM).</span><span class="sxs-lookup"><span data-stu-id="d11b2-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d11b2-553">Ciò include il malware rilevato dalla sequenza di avvio</span><span class="sxs-lookup"><span data-stu-id="d11b2-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d11b2-554">Attestazione remota</span><span class="sxs-lookup"><span data-stu-id="d11b2-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="d11b2-555">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="d11b2-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d11b2-556">Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.</span><span class="sxs-lookup"><span data-stu-id="d11b2-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d11b2-557">Utente </dt> 
<dt>UAC: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt> 
<dt> Action: &lt; Action , ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-558">Clean: la risorsa è stata pulita</span><span class="sxs-lookup"><span data-stu-id="d11b2-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d11b2-559">Quarantena: la risorsa è stata messi in quarantena</span><span class="sxs-lookup"><span data-stu-id="d11b2-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d11b2-560">Rimuovi: la risorsa è stata eliminata</span><span class="sxs-lookup"><span data-stu-id="d11b2-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d11b2-561">Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</span><span class="sxs-lookup"><span data-stu-id="d11b2-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d11b2-562">Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d11b2-563">Nessuna azione: nessuna azione</span><span class="sxs-lookup"><span data-stu-id="d11b2-563">No action: No action</span></span></li>
<li><span data-ttu-id="d11b2-564">Blocca: l'esecuzione della risorsa è stata bloccata</span><span class="sxs-lookup"><span data-stu-id="d11b2-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d11b2-565">
</dt>
<dt>Stato azione: &lt; Descrizione delle &gt; azioni aggiuntive</dt>
<dt>Codice di errore: Codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-566">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-567">Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d11b2-567">No action is necessary.</span></span> <span data-ttu-id="d11b2-568">Antivirus Microsoft Defender non è riuscito a completare un'attività correlata alla correzione del malware.</span><span class="sxs-lookup"><span data-stu-id="d11b2-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="d11b2-569">Non si tratta di un errore critico.</span><span class="sxs-lookup"><span data-stu-id="d11b2-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-570">ID evento: 1119</span><span class="sxs-lookup"><span data-stu-id="d11b2-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-571">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-573">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-573">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-574">
<b>La piattaforma antimalware ha riscontrato un errore critico quando si tenta di intervenire su malware o altro software potenzialmente indesiderato. Nel messaggio dell'evento sono disponibili ulteriori dettagli.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-575">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-576">Antivirus Microsoft Defender si è verificato un errore critico durante l'azione su malware o altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="d11b2-577">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="d11b2-578">
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-579">Bassa</span><span class="sxs-lookup"><span data-stu-id="d11b2-579">Low</span></span></li>
<li><span data-ttu-id="d11b2-580">Moderato</span><span class="sxs-lookup"><span data-stu-id="d11b2-580">Moderate</span></span></li>
<li><span data-ttu-id="d11b2-581">Alta</span><span class="sxs-lookup"><span data-stu-id="d11b2-581">High</span></span></li>
<li><span data-ttu-id="d11b2-582">Grave</span><span class="sxs-lookup"><span data-stu-id="d11b2-582">Severe</span></span></li>
</ul><span data-ttu-id="d11b2-583">
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-584">Unknown</span><span class="sxs-lookup"><span data-stu-id="d11b2-584">Unknown</span></span></li>
<li><span data-ttu-id="d11b2-585">Computer locale</span><span class="sxs-lookup"><span data-stu-id="d11b2-585">Local computer</span></span></li>
<li><span data-ttu-id="d11b2-586">Condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-586">Network share</span></span></li>
<li><span data-ttu-id="d11b2-587">Internet</span><span class="sxs-lookup"><span data-stu-id="d11b2-587">Internet</span></span></li>
<li><span data-ttu-id="d11b2-588">Traffico in ingresso</span><span class="sxs-lookup"><span data-stu-id="d11b2-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="d11b2-589">Traffico in uscita</span><span class="sxs-lookup"><span data-stu-id="d11b2-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="d11b2-590">
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-591">Euristica</span><span class="sxs-lookup"><span data-stu-id="d11b2-591">Heuristics</span></span></li>
<li><span data-ttu-id="d11b2-592">Generale</span><span class="sxs-lookup"><span data-stu-id="d11b2-592">Generic</span></span></li>
<li><span data-ttu-id="d11b2-593">Concrete</span><span class="sxs-lookup"><span data-stu-id="d11b2-593">Concrete</span></span></li>
<li><span data-ttu-id="d11b2-594">Firma dinamica</span><span class="sxs-lookup"><span data-stu-id="d11b2-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="d11b2-595">
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="d11b2-596">Utente: avviato dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-596">User: user initiated</span></span></li>
<li><span data-ttu-id="d11b2-597">Sistema: sistema avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-597">System: system initiated</span></span></li>
<li><span data-ttu-id="d11b2-598">Tempo reale: componente in tempo reale avviato</span><span class="sxs-lookup"><span data-stu-id="d11b2-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="d11b2-599">IOAV: download di Internet Outlook express allegati avviati</span><span class="sxs-lookup"><span data-stu-id="d11b2-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="d11b2-600">NIS: sistema di ispezione della rete</span><span class="sxs-lookup"><span data-stu-id="d11b2-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="d11b2-601">IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</span><span class="sxs-lookup"><span data-stu-id="d11b2-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="d11b2-602">Antimalware di avvio anticipato (ELAM).</span><span class="sxs-lookup"><span data-stu-id="d11b2-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="d11b2-603">Ciò include il malware rilevato dalla sequenza di avvio</span><span class="sxs-lookup"><span data-stu-id="d11b2-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="d11b2-604">Attestazione remota</span><span class="sxs-lookup"><span data-stu-id="d11b2-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="d11b2-605">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="d11b2-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="d11b2-606">Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.</span><span class="sxs-lookup"><span data-stu-id="d11b2-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="d11b2-607">Utente </dt> 
<dt>UAC: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt> 
<dt> Action: &lt; Action , ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="d11b2-608">Clean: la risorsa è stata pulita</span><span class="sxs-lookup"><span data-stu-id="d11b2-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="d11b2-609">Quarantena: la risorsa è stata messi in quarantena</span><span class="sxs-lookup"><span data-stu-id="d11b2-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="d11b2-610">Rimuovi: la risorsa è stata eliminata</span><span class="sxs-lookup"><span data-stu-id="d11b2-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="d11b2-611">Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</span><span class="sxs-lookup"><span data-stu-id="d11b2-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="d11b2-612">Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="d11b2-613">Nessuna azione: nessuna azione</span><span class="sxs-lookup"><span data-stu-id="d11b2-613">No action: No action</span></span></li>
<li><span data-ttu-id="d11b2-614">Blocca: l'esecuzione della risorsa è stata bloccata</span><span class="sxs-lookup"><span data-stu-id="d11b2-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="d11b2-615">
</dt>
<dt>Stato azione: &lt; Descrizione delle &gt; azioni aggiuntive</dt>
<dt>Codice di errore: Codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-616">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-617">Il Antivirus Microsoft Defender client ha riscontrato questo errore a causa di problemi critici.</span><span class="sxs-lookup"><span data-stu-id="d11b2-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="d11b2-618">L'endpoint potrebbe non essere protetto.</span><span class="sxs-lookup"><span data-stu-id="d11b2-618">The endpoint might not be protected.</span></span> <span data-ttu-id="d11b2-619">Esamina la descrizione dell'errore e segui i passaggi <b>pertinenti per l'azione dell'utente</b> riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="d11b2-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="d11b2-620">Azione</span><span class="sxs-lookup"><span data-stu-id="d11b2-620">Action</span></span></th>
<th><span data-ttu-id="d11b2-621">Azione utente</span><span class="sxs-lookup"><span data-stu-id="d11b2-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="d11b2-622">
<b>Rimuovi</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="d11b2-623">Aggiornare le definizioni, quindi verificare che la rimozione sia stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="d11b2-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="d11b2-624">
<b>Clean</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="d11b2-625">Aggiornare le definizioni, quindi verificare che la correzione sia stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="d11b2-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="d11b2-626">
<b>Quarantena</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="d11b2-627">Aggiornare le definizioni e verificare che l'utente sia autorizzato ad accedere alle risorse necessarie.</span><span class="sxs-lookup"><span data-stu-id="d11b2-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="d11b2-628">
<b>Consenti</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="d11b2-629">Verificare che l'utente sia autorizzato ad accedere alle risorse necessarie.</span><span class="sxs-lookup"><span data-stu-id="d11b2-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="d11b2-630">Se questo evento persiste:</span><span class="sxs-lookup"><span data-stu-id="d11b2-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="d11b2-631">Eseguire di nuovo l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="d11b2-632">Se si verifica un errore nello stesso modo, accedere al <b></b> sito del Supporto <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Tecnico Microsoft,</a>immettere il numero di errore nella casella Cerca per cercare il codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="d11b2-633">Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-634">ID evento: 1120</span><span class="sxs-lookup"><span data-stu-id="d11b2-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-635">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-637">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-637">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-638">
<b>Antivirus Microsoft Defender ha dedotto gli hash per una risorsa di minaccia.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-639">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-640">Antivirus Microsoft Defender client è attivo e in esecuzione in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="d11b2-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="d11b2-641">
<dt>Versione piattaforma corrente: &lt; Current platform &gt; version</dt>
<dt>Threat Resource Path: &lt; Path &gt; </dt>
<dt>Hashes: &lt; Hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="d11b2-642"><b>Nota: questo evento verrà registrato solo se è impostato il criterio seguente: <b>ThreatFileHashLogging unsigned</b>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-643">ID evento: 1150</span><span class="sxs-lookup"><span data-stu-id="d11b2-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-644">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-646">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-646">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-647">
<b>Se la piattaforma antimalware segnala lo stato a una piattaforma di monitoraggio, questo evento indica che la piattaforma antimalware è in esecuzione e in uno stato integro. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-648">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-649">Antivirus Microsoft Defender client è attivo e in esecuzione in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="d11b2-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="d11b2-650">
<dt>Versione piattaforma: &lt; Versione corrente &gt; della piattaforma</dt>
<dt>Versione firma: versione di &lt; definizione &gt; </dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-651">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-652">Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d11b2-652">No action is necessary.</span></span> <span data-ttu-id="d11b2-653">Il Antivirus Microsoft Defender client è in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="d11b2-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="d11b2-654">Questo evento viene segnalato ogni ora.</span><span class="sxs-lookup"><span data-stu-id="d11b2-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="d11b2-655">ID evento: 1151</span><span class="sxs-lookup"><span data-stu-id="d11b2-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-656">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-658">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-658">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-659">
<b>Endpoint Protection stato del client (ora UTC)</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-660">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-661">Rapporto integrità client antivirus.</span><span class="sxs-lookup"><span data-stu-id="d11b2-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="d11b2-662">
<dt>Versione piattaforma: &lt; &gt;</dt>Versione corrente della piattaforma Versione motore
<dt> &lt; Antimalware Engine: &gt; </dt>versione del motore di ispezione in tempo reale di
<dt>rete: &lt; &gt; </dt>versione del motore di ispezione in tempo reale di rete Versione firma
<dt>antivirus: &lt; &gt; </dt>versione firma antivirus Versione firma
<dt> &lt; antispyware: &gt; </dt>versione firma antispyware Versione firma Network
<dt>Realtime Inspection: &lt; &gt; </dt>Stato RTP versione firma ispezione in tempo reale di rete: Stato OA in tempo reale
<dt> &lt; &gt; (abilitato</dt>o disabilitato): stato di
<dt>IE (Abilitato o &lt; &gt; Disabilitato)</dt>Download e stato Outlook Express Attachments (Abilitato o
<dt> &lt; &gt; Disabilitato)</dt>
<dt>Stato BM: Stato monitoraggio del comportamento (Abilitato o &lt; &gt; Disabilitato)</dt>Validità firma antivirus: validità firma antivirus
<dt> &lt; &gt; (in giorni)</dt>Validità firma antispyware: Validità firma
<dt> &lt; antispyware &gt; (in giorni)</dt>Durata ultima analisi rapida: Validità ultima analisi rapida
<dt> &lt; &gt; (in giorni)</dt>Validità ultima analisi completa: Validità ultima analisi
<dt>completa &lt; &gt; (in giorni)</dt>Durata creazione firma
<dt>antivirus: ? &lt; Tempo creazione &gt; firma antivirus</dt>
<dt>Tempo creazione firma Antispyware: ? &lt; Ora creazione firma &gt; antispyware</dt>Ultima ora di avvio
<dt>dell'analisi rapida: ? &lt; Ora ultima inizio &gt; analisi rapida</dt>
<dt>Ultima ora di fine analisi rapida: ? &lt; &gt;</dt>Ora di fine ultima analisi rapida Ultima origine di analisi rapida: Ultima origine di analisi rapida (0&#39;= analisi non eseguita, 1 = avviata dall'utente, 2 = avviata dal
<dt> &lt; &gt; sistema)</dt>Ultima ora di avvio dell'analisi
<dt>completa: ? &lt; Ultima ora di &gt; inizio dell'analisi completa</dt>
<dt>Ultima ora di fine analisi completa: ? &lt; Ora &gt; </dt>di fine ultima analisi completa Ultima origine analisi completa: Ultima origine analisi completa (0&#39;= analisi non eseguita, 1 = avviata dall'utente, 2 = avviata dal
<dt> &lt; &gt; sistema)</dt>Stato del prodotto: per la risoluzione dei problemi 
<dt> interni</span><span class="sxs-lookup"><span data-stu-id="d11b2-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="d11b2-663">
<th colspan="2">ID evento: 2000</span><span class="sxs-lookup"><span data-stu-id="d11b2-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-664">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-666">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-666">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-667">
<b>Le definizioni antimalware sono state aggiornate correttamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-668">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-669">La versione della firma antivirus è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="d11b2-670">
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt>
<dt>Versione firma precedente: versione firma &lt; precedente &gt; </dt>Tipo di 
<dt> firma: Tipo di &lt; &gt; firma, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d11b2-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-671">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-672">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-673">Antimalware</span></span></li>
<li><span data-ttu-id="d11b2-674">Network Inspection System</span><span class="sxs-lookup"><span data-stu-id="d11b2-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d11b2-675">
</dt>
<dt>Tipo di aggiornamento: &lt; Tipo di &gt; aggiornamento , Completo o Delta.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-676">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-677">Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d11b2-677">No action is necessary.</span></span> <span data-ttu-id="d11b2-678">Il Antivirus Microsoft Defender client è in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="d11b2-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="d11b2-679">Questo evento viene segnalato quando le firme vengono aggiornate correttamente.</span><span class="sxs-lookup"><span data-stu-id="d11b2-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-680">ID evento: 2001</span><span class="sxs-lookup"><span data-stu-id="d11b2-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-681">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-683">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-683">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-684">
<b>L'aggiornamento della sicurezza intelligence non è riuscito. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-685">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-686">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di aggiornare le firme.</span><span class="sxs-lookup"><span data-stu-id="d11b2-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="d11b2-687">
<dt>Nuova versione di security intelligence: &lt; Nuovo numero &gt; di versione</dt>
<dt>Versione intelligence di sicurezza precedente: Versione &lt; precedente &gt; </dt> 
<dt> Origine aggiornamento: Origine &lt; &gt; aggiornamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-688">Cartella di aggiornamento delle funzionalità di intelligence per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d11b2-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="d11b2-689">Server di aggiornamento intelligence per la sicurezza interna</span><span class="sxs-lookup"><span data-stu-id="d11b2-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="d11b2-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="d11b2-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="d11b2-691">Condivisione file</span><span class="sxs-lookup"><span data-stu-id="d11b2-691">File share</span></span></li>
<li><span data-ttu-id="d11b2-692">Microsoft Malware Protection Center (MMPC)</span><span class="sxs-lookup"><span data-stu-id="d11b2-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="d11b2-693">
</dt>
<dt>Fase di aggiornamento: &lt; fase di &gt; aggiornamento, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-694">Ricerca</span><span class="sxs-lookup"><span data-stu-id="d11b2-694">Search</span></span></li>
<li><span data-ttu-id="d11b2-695">Scarica</span><span class="sxs-lookup"><span data-stu-id="d11b2-695">Download</span></span></li>
<li><span data-ttu-id="d11b2-696">Installare</span><span class="sxs-lookup"><span data-stu-id="d11b2-696">Install</span></span></li>
</ul><span data-ttu-id="d11b2-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Tipo di firma: &lt; Tipo di &gt; firma, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d11b2-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-698">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-699">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-700">Antimalware</span></span></li>
<li><span data-ttu-id="d11b2-701">Network Inspection System</span><span class="sxs-lookup"><span data-stu-id="d11b2-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d11b2-702">
</dt>
<dt>Tipo di aggiornamento: &lt; Tipo di &gt; aggiornamento , Completo o Delta.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-703">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-704">Questo errore si verifica quando si verifica un problema durante l'aggiornamento delle definizioni.</span><span class="sxs-lookup"><span data-stu-id="d11b2-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="d11b2-705">Per risolvere i problemi relativi a questo evento:</span><span class="sxs-lookup"><span data-stu-id="d11b2-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d11b2-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aggiornare le definizioni</a> e forzare una nuova analisi direttamente nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d11b2-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="d11b2-707">Esaminare le voci nel file %Windir%\WindowsUpdate.log per ulteriori informazioni su questo errore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="d11b2-708">Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-709">ID evento: 2002</span><span class="sxs-lookup"><span data-stu-id="d11b2-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-710">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-712">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-712">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-713">
<b>Il motore antimalware è stato aggiornato correttamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-714">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-715">Antivirus Microsoft Defender versione del motore è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="d11b2-716">
<dt>Versione motore corrente: &lt; Versione corrente &gt; del motore</dt>Versione motore
<dt>precedente: &lt; &gt; Versione</dt>precedente motore Tipo di motore: Tipo di motore, motore
<dt> &lt; antimalware o motore di Network Inspection &gt; System.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; Utente &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-717">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-718">Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d11b2-718">No action is necessary.</span></span> <span data-ttu-id="d11b2-719">Il Antivirus Microsoft Defender client è in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="d11b2-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="d11b2-720">Questo evento viene segnalato quando il motore antimalware viene aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d11b2-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-721">ID evento: 2003</span><span class="sxs-lookup"><span data-stu-id="d11b2-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-722">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-724">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-724">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-725">
<b>Aggiornamento del motore antimalware non riuscito. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-726">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-727">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di aggiornare il motore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="d11b2-728">
<dt>Nuova versione del motore:</dt>versione precedente
<dt>del motore: &lt; &gt; versione</dt>precedente Tipo di motore: Tipo di motore, motore
<dt>antimalware o motore del sistema di ispezione di &lt; &gt; rete.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-729">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-730">L'Antivirus Microsoft Defender client non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="d11b2-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="d11b2-731">Questo evento si verifica quando il client non riesce ad aggiornarsi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="d11b2-732">Questo evento è in genere dovuto a un'interruzione della connettività di rete durante un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d11b2-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="d11b2-733">Per risolvere i problemi relativi a questo evento:</span><span class="sxs-lookup"><span data-stu-id="d11b2-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d11b2-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aggiornare le definizioni</a> e forzare una nuova analisi direttamente nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d11b2-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="d11b2-735">Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-736">ID evento: 2004</span><span class="sxs-lookup"><span data-stu-id="d11b2-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-737">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-739">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-739">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-740">
<b>Si è verificato un problema durante il caricamento delle definizioni antimalware. Il motore antimalware tenterà di caricare l'ultimo set di definizioni valido noto.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-741">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-742">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di caricare le firme e tenterà di ripristinare un set di firme valido.</span><span class="sxs-lookup"><span data-stu-id="d11b2-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="d11b2-743">
<dt>Firme tentate:</dt>
<dt>Codice di errore: codice di errore Codice di risultato associato allo stato della &lt; &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: versione &lt; &gt; del motore antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-744">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-745">Il Antivirus Microsoft Defender ha tentato di scaricare e installare il file di definizioni più recente e non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="d11b2-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="d11b2-746">Questo errore può verificarsi quando il client rileva un errore durante il tentativo di caricamento delle definizioni o se il file è danneggiato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="d11b2-747">Antivirus Microsoft Defender tenterà di ripristinare un set di definizioni noto.</span><span class="sxs-lookup"><span data-stu-id="d11b2-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="d11b2-748">Per risolvere i problemi relativi a questo evento:</span><span class="sxs-lookup"><span data-stu-id="d11b2-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d11b2-749">Riavviare il computer e riprovare.</span><span class="sxs-lookup"><span data-stu-id="d11b2-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="d11b2-750">Scaricare le definizioni più recenti <a href="https://aka.ms/wdsi">dal sito Intelligence di sicurezza Microsoft .</a></span><span class="sxs-lookup"><span data-stu-id="d11b2-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="d11b2-751">Nota: le dimensioni del file di definizioni scaricato dal sito possono superare i 60 MB e non devono essere utilizzate come soluzione a lungo termine per l'aggiornamento delle definizioni.</span><span class="sxs-lookup"><span data-stu-id="d11b2-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="d11b2-752">Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-753">ID evento: 2005</span><span class="sxs-lookup"><span data-stu-id="d11b2-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-754">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-756">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-756">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-757">
<b>Impossibile caricare il motore antimalware perché la piattaforma antimalware non è aggiornata. La piattaforma antimalware carica l'ultimo motore antimalware valido noto e tenta di aggiornarsi.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-758">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-759">Antivirus Microsoft Defender non è stato possibile caricare il motore antimalware perché la versione corrente della piattaforma non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="d11b2-760">Antivirus Microsoft Defender verrà ripristinato l'ultimo motore noto e verrà eseguito un tentativo di aggiornamento della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="d11b2-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="d11b2-761">
<dt>Versione corrente della piattaforma: &lt; versione corrente della piattaforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-762">ID evento: 2006</span><span class="sxs-lookup"><span data-stu-id="d11b2-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-763">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-765">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-765">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-766">
<b>Aggiornamento della piattaforma non riuscito. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-767">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-768">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di aggiornare la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="d11b2-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="d11b2-769">
<dt>Versione piattaforma corrente: &lt; Versione corrente &gt; della piattaforma</dt>
<dt>Codice di errore: codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-770">ID evento: 2007</span><span class="sxs-lookup"><span data-stu-id="d11b2-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-771">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-773">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-773">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-774">
<b>La piattaforma sarà presto non aggiornata. Scarica la piattaforma più recente per mantenere una protezione aggiornata.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-775">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-776">Antivirus Microsoft Defender presto sarà necessaria una versione della piattaforma più recente per supportare le versioni future del motore antimalware.</span><span class="sxs-lookup"><span data-stu-id="d11b2-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="d11b2-777">Scarica la piattaforma Antivirus Microsoft Defender più recente per mantenere il miglior livello di protezione disponibile.</span><span class="sxs-lookup"><span data-stu-id="d11b2-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="d11b2-778">
<dt>Versione corrente della piattaforma: &lt; versione corrente della piattaforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-779">ID evento: 2010</span><span class="sxs-lookup"><span data-stu-id="d11b2-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-780">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-782">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-782">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-783">
<b>Il motore antimalware ha utilizzato il servizio di firma dinamico per ottenere ulteriori definizioni. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-784">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-785">Antivirus Microsoft Defender <i>utilizzato dynamic signature service</i> per recuperare firme aggiuntive per proteggere il computer.</span><span class="sxs-lookup"><span data-stu-id="d11b2-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="d11b2-786">
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt> 
<dt> Tipo di firma: Tipo di &lt; &gt; firma, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d11b2-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-787">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-788">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-789">Antimalware</span></span></li>
<li><span data-ttu-id="d11b2-790">Network Inspection System</span><span class="sxs-lookup"><span data-stu-id="d11b2-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d11b2-791">
</dt>
<dt>Versione motore corrente: &lt; Versione motore &gt; corrente</dt> 
<dt> Tipo di firma dinamica: tipo di firma &lt; &gt; dinamica, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-792">Version</span><span class="sxs-lookup"><span data-stu-id="d11b2-792">Version</span></span></li>
<li><span data-ttu-id="d11b2-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d11b2-793">Timestamp</span></span></li>
<li><span data-ttu-id="d11b2-794">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="d11b2-794">No limit</span></span></li>
<li><span data-ttu-id="d11b2-795">Durata</span><span class="sxs-lookup"><span data-stu-id="d11b2-795">Duration</span></span></li>
</ul><span data-ttu-id="d11b2-796">
</dt>
<dt>Percorso di persistenza: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Persistence Limit 
<dt> Type: Persistence limit type , ad &lt; &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-797">Versione VDM</span><span class="sxs-lookup"><span data-stu-id="d11b2-797">VDM version</span></span></li>
<li><span data-ttu-id="d11b2-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d11b2-798">Timestamp</span></span></li>
<li><span data-ttu-id="d11b2-799">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="d11b2-799">No limit</span></span></li>
</ul><span data-ttu-id="d11b2-800">
</dt>
<dt>Limite di persistenza: limite di persistenza della firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-801">ID evento: 2011</span><span class="sxs-lookup"><span data-stu-id="d11b2-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-802">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-804">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-804">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-805">
<b>Il servizio di firma dinamica ha eliminato le definizioni dinamiche non aggiornate. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-806">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-807">Antivirus Microsoft Defender il <i>servizio di firma dinamico per</i> eliminare le firme obsolete.</span><span class="sxs-lookup"><span data-stu-id="d11b2-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="d11b2-808">
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt> 
<dt> Tipo di firma: Tipo di &lt; &gt; firma, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d11b2-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-809">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-810">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-811">Antimalware</span></span></li>
<li><span data-ttu-id="d11b2-812">Network Inspection System</span><span class="sxs-lookup"><span data-stu-id="d11b2-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d11b2-813">
</dt>
<dt>Versione motore corrente: &lt; Versione motore &gt; corrente</dt> 
<dt> Tipo di firma dinamica: tipo di firma &lt; &gt; dinamica, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-814">Version</span><span class="sxs-lookup"><span data-stu-id="d11b2-814">Version</span></span></li>
<li><span data-ttu-id="d11b2-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d11b2-815">Timestamp</span></span></li>
<li><span data-ttu-id="d11b2-816">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="d11b2-816">No limit</span></span></li>
<li><span data-ttu-id="d11b2-817">Durata</span><span class="sxs-lookup"><span data-stu-id="d11b2-817">Duration</span></span></li>
</ul><span data-ttu-id="d11b2-818">
</dt>
<dt>Percorso di persistenza: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: Persistence limit type , ad &lt; &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-819">Versione VDM</span><span class="sxs-lookup"><span data-stu-id="d11b2-819">VDM version</span></span></li>
<li><span data-ttu-id="d11b2-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d11b2-820">Timestamp</span></span></li>
<li><span data-ttu-id="d11b2-821">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="d11b2-821">No limit</span></span></li>
</ul><span data-ttu-id="d11b2-822">
</dt>
<dt>Limite di persistenza: limite di persistenza della firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-823">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-824">Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d11b2-824">No action is necessary.</span></span> <span data-ttu-id="d11b2-825">Il Antivirus Microsoft Defender client è in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="d11b2-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="d11b2-826">Questo evento viene segnalato quando il servizio di firma dinamica elimina correttamente le definizioni dinamiche non aggiornate.</span><span class="sxs-lookup"><span data-stu-id="d11b2-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-827">ID evento: 2012</span><span class="sxs-lookup"><span data-stu-id="d11b2-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-828">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-830">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-830">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-831">
<b>Il motore antimalware ha riscontrato un errore durante il tentativo di utilizzare il servizio di firma dinamico. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-832">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-833">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di utilizzo <i>del servizio di firma dinamico.</i></span><span class="sxs-lookup"><span data-stu-id="d11b2-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="d11b2-834">
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt> 
<dt> Tipo di firma: Tipo di &lt; &gt; firma, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="d11b2-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d11b2-835">Antivirus</span></span></li>
<li><span data-ttu-id="d11b2-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="d11b2-836">Antispyware</span></span></li>
<li><span data-ttu-id="d11b2-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="d11b2-837">Antimalware</span></span></li>
<li><span data-ttu-id="d11b2-838">Network Inspection System</span><span class="sxs-lookup"><span data-stu-id="d11b2-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d11b2-839">
</dt>
<dt>Versione motore corrente: &lt; Versione corrente &gt; del motore</dt>
<dt>Codice di errore: codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt> Tipo di firma dinamica: &lt; tipo di firma &gt; dinamico, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-840">Version</span><span class="sxs-lookup"><span data-stu-id="d11b2-840">Version</span></span></li>
<li><span data-ttu-id="d11b2-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d11b2-841">Timestamp</span></span></li>
<li><span data-ttu-id="d11b2-842">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="d11b2-842">No limit</span></span></li>
<li><span data-ttu-id="d11b2-843">Durata</span><span class="sxs-lookup"><span data-stu-id="d11b2-843">Duration</span></span></li>
</ul><span data-ttu-id="d11b2-844">
</dt>
<dt>Percorso di persistenza: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Persistence Limit 
<dt> Type: Persistence limit type , ad &lt; &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-845">Versione VDM</span><span class="sxs-lookup"><span data-stu-id="d11b2-845">VDM version</span></span></li>
<li><span data-ttu-id="d11b2-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d11b2-846">Timestamp</span></span></li>
<li><span data-ttu-id="d11b2-847">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="d11b2-847">No limit</span></span></li>
</ul><span data-ttu-id="d11b2-848">
</dt>
<dt>Limite di persistenza: limite di persistenza della firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-849">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-850">Controllare le impostazioni di connettività Internet.</span><span class="sxs-lookup"><span data-stu-id="d11b2-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-851">ID evento: 2013</span><span class="sxs-lookup"><span data-stu-id="d11b2-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-852">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-854">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-854">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-855">
<b>Il servizio di firma dinamica ha eliminato tutte le definizioni dinamiche. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-856">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-857">Antivirus Microsoft Defender tutte le firme <i>del servizio di firma</i> dinamica.</span><span class="sxs-lookup"><span data-stu-id="d11b2-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="d11b2-858">
<dt>Versione firma corrente: &lt; versione della firma corrente&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-859">ID evento: 2020</span><span class="sxs-lookup"><span data-stu-id="d11b2-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-860">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-862">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-862">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-863">
<b>Il motore antimalware ha scaricato un file pulito. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-864">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-865">Antivirus Microsoft Defender scaricato un file pulito.</span><span class="sxs-lookup"><span data-stu-id="d11b2-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="d11b2-866">
<dt>Nome file: &lt; Nome file &gt; Nome del file.</dt> 
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt>
<dt>Versione motore corrente: versione corrente del &lt; motore &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-867">ID evento: 2021</span><span class="sxs-lookup"><span data-stu-id="d11b2-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-868">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-870">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-870">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-871">
<b>Il motore antimalware non è riuscito a scaricare un file pulito. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-872">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-873">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di scaricare un file pulito.</span><span class="sxs-lookup"><span data-stu-id="d11b2-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="d11b2-874">
<dt>Nome file: &lt; Nome file &gt; Nome del file.</dt> 
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt>
<dt>Versione motore corrente: versione &lt; &gt; corrente del motore</dt>Codice di errore: codice di errore Codice di errore Codice di risultato associato allo stato della
<dt> &lt; &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-875">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-876">Controllare le impostazioni di connettività Internet.</span><span class="sxs-lookup"><span data-stu-id="d11b2-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="d11b2-877">Il client Antivirus Microsoft Defender ha riscontrato un errore quando si utilizza il servizio di firma dinamico per scaricare le definizioni più recenti in una minaccia specifica.</span><span class="sxs-lookup"><span data-stu-id="d11b2-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="d11b2-878">Questo errore è probabilmente causato da un problema di connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="d11b2-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-879">ID evento: 2030</span><span class="sxs-lookup"><span data-stu-id="d11b2-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-880">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-882">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-882">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-883">
<b>Il motore antimalware è stato scaricato ed è configurato per l'esecuzione offline al successivo riavvio del sistema.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-884">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-885">Antivirus Microsoft Defender antivirus offline scaricato e configurato per l'esecuzione al riavvio successivo.</span><span class="sxs-lookup"><span data-stu-id="d11b2-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-886">ID evento: 2031</span><span class="sxs-lookup"><span data-stu-id="d11b2-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-887">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-889">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-889">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-890">
<b>Il motore antimalware non è stato in grado di scaricare e configurare un'analisi offline.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-891">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-892">Antivirus Microsoft Defender si è verificato un errore durante il tentativo di scaricare e configurare l'antivirus offline.</span><span class="sxs-lookup"><span data-stu-id="d11b2-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="d11b2-893">
<dt>Codice errore: &lt; Codice di errore &gt; Codice di risultato associato allo stato della minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-894">ID evento: 2040</span><span class="sxs-lookup"><span data-stu-id="d11b2-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-895">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-897">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-897">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-898">
<b>Il supporto antimalware per questa versione del sistema operativo terminerà presto. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-899">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-900">Il supporto per il sistema operativo scadrà a breve.</span><span class="sxs-lookup"><span data-stu-id="d11b2-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="d11b2-901">L'Antivirus Microsoft Defender in un sistema operativo fuori supporto non è una soluzione adeguata per la protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="d11b2-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-902">ID evento: 2041</span><span class="sxs-lookup"><span data-stu-id="d11b2-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-903">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-905">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-905">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-906">
<b>Il supporto antimalware per questo sistema operativo è terminato. È necessario aggiornare il sistema operativo per continuare a supportare. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-907">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-908">Il supporto per il sistema operativo è scaduto.</span><span class="sxs-lookup"><span data-stu-id="d11b2-908">The support for your operating system has expired.</span></span> <span data-ttu-id="d11b2-909">L'Antivirus Microsoft Defender in un sistema operativo fuori supporto non è una soluzione adeguata per la protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="d11b2-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-910">ID evento: 2042</span><span class="sxs-lookup"><span data-stu-id="d11b2-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-911">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-913">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-913">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-914">
<b>Il motore antimalware non supporta più questo sistema operativo e non protegge più il sistema da malware. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-915">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-916">Il supporto per il sistema operativo è scaduto.</span><span class="sxs-lookup"><span data-stu-id="d11b2-916">The support for your operating system has expired.</span></span> <span data-ttu-id="d11b2-917">Antivirus Microsoft Defender non è più supportato nel sistema operativo, ha smesso di funzionare e non protegge dalle minacce malware.</span><span class="sxs-lookup"><span data-stu-id="d11b2-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-918">ID evento: 3002</span><span class="sxs-lookup"><span data-stu-id="d11b2-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-919">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-921">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-921">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-922">
<b>La protezione in tempo reale ha riscontrato un errore e non è riuscita.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-923">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-924">Antivirus Microsoft Defender Real-Time funzionalità di protezione ha riscontrato un errore e non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d11b2-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="d11b2-925">
<dt>Funzionalità: &lt; funzionalità , ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-926">On Access</span><span class="sxs-lookup"><span data-stu-id="d11b2-926">On Access</span></span></li>
<li><span data-ttu-id="d11b2-927">Download di Internet Explorer e allegati di Microsoft Outlook Express</span><span class="sxs-lookup"><span data-stu-id="d11b2-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="d11b2-928">Monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="d11b2-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="d11b2-929">Network Inspection System</span><span class="sxs-lookup"><span data-stu-id="d11b2-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d11b2-930">
</dt>
<dt>Codice errore: &lt; Codice di errore &gt; Codice di risultato associato allo stato della minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Motivo: il motivo Antivirus Microsoft Defender protezione in tempo reale ha riavviato una funzionalità.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-931">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-932">È consigliabile riavviare il sistema e quindi eseguire un'analisi completa&#39;possibile che il sistema non sia stato protetto per un certo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d11b2-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="d11b2-933">Il Antivirus Microsoft Defender client&#39;funzionalità di protezione in tempo reale ha riscontrato un errore perché non è stato possibile avviare uno dei servizi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="d11b2-934">Se è seguito da un ID evento 3007, l'errore è stato temporaneo e il client antimalware è stato ripristinato dall'errore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-935">ID evento: 3007</span><span class="sxs-lookup"><span data-stu-id="d11b2-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-936">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-938">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-938">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-939">
<b>Protezione in tempo reale recuperata da un errore. È consigliabile eseguire un'analisi completa del sistema quando viene visualizzato questo errore. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-940">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-941">Antivirus Microsoft Defender Protezione in tempo reale ha riavviato una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d11b2-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="d11b2-942">È consigliabile eseguire un'analisi completa del sistema per rilevare eventuali elementi che potrebbero essere stati persi mentre l'agente non era in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d11b2-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="d11b2-943">
<dt>Funzionalità: &lt; funzionalità , ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-944">On Access</span><span class="sxs-lookup"><span data-stu-id="d11b2-944">On Access</span></span></li>
<li><span data-ttu-id="d11b2-945">Download di IE e allegati Outlook Express</span><span class="sxs-lookup"><span data-stu-id="d11b2-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="d11b2-946">Monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="d11b2-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="d11b2-947">Network Inspection System</span><span class="sxs-lookup"><span data-stu-id="d11b2-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d11b2-948">
</dt>
<dt>Motivo: il motivo Antivirus Microsoft Defender protezione in tempo reale ha riavviato una funzionalità.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-949">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-950">La funzionalità di protezione in tempo reale è stata riavviata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="d11b2-951">Se questo evento si verifica di nuovo, contattare il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="d11b2-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-952">ID evento: 5000</span><span class="sxs-lookup"><span data-stu-id="d11b2-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-953">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-955">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-955">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-956">
<b>La protezione in tempo reale è abilitata. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-957">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-958">Antivirus Microsoft Defender l'analisi della protezione in tempo reale per malware e altro software potenzialmente indesiderato è stato abilitato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-959">ID evento: 5001</span><span class="sxs-lookup"><span data-stu-id="d11b2-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-960">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-962">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-962">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-963">
<b>La protezione in tempo reale è disabilitata. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-964">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-965">Antivirus Microsoft Defender'analisi della protezione in tempo reale per malware e altro software potenzialmente indesiderato è stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-966">ID evento: 5004</span><span class="sxs-lookup"><span data-stu-id="d11b2-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-967">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-969">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-969">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-970">
<b>La configurazione della protezione in tempo reale è cambiata. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-971">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-972">Antivirus Microsoft Defender configurazione delle funzionalità di protezione in tempo reale è cambiata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="d11b2-973">
<dt>Funzionalità: &lt; funzionalità , ad &gt; esempio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="d11b2-974">On Access</span><span class="sxs-lookup"><span data-stu-id="d11b2-974">On Access</span></span></li>
<li><span data-ttu-id="d11b2-975">Download di IE e allegati Outlook Express</span><span class="sxs-lookup"><span data-stu-id="d11b2-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="d11b2-976">Monitoraggio del comportamento</span><span class="sxs-lookup"><span data-stu-id="d11b2-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="d11b2-977">Network Inspection System</span><span class="sxs-lookup"><span data-stu-id="d11b2-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="d11b2-978">
</dt>
<dt>Configurazione: </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-979">ID evento: 5007</span><span class="sxs-lookup"><span data-stu-id="d11b2-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-980">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-982">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-982">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-983">
<b>La configurazione della piattaforma antimalware è cambiata.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-984">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-985">Antivirus Microsoft Defender configurazione è cambiata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="d11b2-986">Se si tratta di un evento imprevisto, è consigliabile esaminare le impostazioni perché questo potrebbe essere il risultato di malware.</span><span class="sxs-lookup"><span data-stu-id="d11b2-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="d11b2-987">
<dt>Valore precedente: &lt; Old value number &gt; Vecchio valore di configurazione antivirus.</dt> 
<dt>Nuovo valore: &lt; Nuovo numero di valore &gt; Nuovo valore di configurazione antivirus.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-988">ID evento: 5008</span><span class="sxs-lookup"><span data-stu-id="d11b2-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-989">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-991">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-991">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-992">
<b>Il motore antimalware ha rilevato un errore e non è riuscito.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-993">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-994">Antivirus Microsoft Defender motore è stato terminato a causa di un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="d11b2-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="d11b2-995">
<dt>Tipo errore: &lt; Tipo di &gt; errore, ad esempio: Codice di eccezione di arresto</dt>anomalo o
<dt>blocco: codice di &lt; &gt; errore</dt>
<dt>Risorsa: &lt; risorsa &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-996">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-997">Per risolvere i problemi relativi a questo evento:</span><span class="sxs-lookup"><span data-stu-id="d11b2-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="d11b2-998">Provare a riavviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d11b2-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="d11b2-999">Per antimalware, antivirus e spyware, al prompt dei comandi con privilegi elevati digitare <b>net stop msmpsvc</b>e quindi digitare <b>net start msmpsvc</b> per riavviare il motore antimalware.</span><span class="sxs-lookup"><span data-stu-id="d11b2-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="d11b2-1000">Per <i>Network Inspection System</i>, al prompt dei comandi con privilegi elevati digitare <b>net start nissrv</b>e quindi <b>digitare net start nissrv</b> per riavviare il motore <i>di Network Inspection System</i> utilizzando il file NiSSRV.exe.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="d11b2-1001">Se non riesce nello stesso modo, cercare il codice di errore accedendo al <b></b> sito di supporto <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> e immettendo il numero di errore nella casella di ricerca e contattare il Supporto tecnico <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="d11b2-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1002">Azione utente:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-1003">Il Antivirus Microsoft Defender client è stato arrestato a causa di un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="d11b2-1004">Per risolvere i problemi relativi a questo evento:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="d11b2-1005">Eseguire di nuovo l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="d11b2-1006">Se si verifica un errore nello stesso modo, accedere al <b></b> sito del Supporto <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Tecnico Microsoft,</a>immettere il numero di errore nella casella Cerca per cercare il codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="d11b2-1007">Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1008">ID evento: 5009</span><span class="sxs-lookup"><span data-stu-id="d11b2-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-1009">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1011">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1012">
<b>La ricerca di malware e altro software potenzialmente indesiderato è abilitata. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1013">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-1014">Antivirus Microsoft Defender è stata abilitata la ricerca di malware e altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1015">ID evento: 5010</span><span class="sxs-lookup"><span data-stu-id="d11b2-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-1016">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1018">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1019">
<b>La ricerca di malware e altro software potenzialmente indesiderato è disabilitata.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1020">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-1021">Antivirus Microsoft Defender la ricerca di malware e altro software potenzialmente indesiderato è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1022">ID evento: 5011</span><span class="sxs-lookup"><span data-stu-id="d11b2-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-1023">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1025">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1026">
<b>La ricerca di virus è abilitata.</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1027">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-1028">Antivirus Microsoft Defender la ricerca di virus è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1029">ID evento: 5012</span><span class="sxs-lookup"><span data-stu-id="d11b2-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-1030">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1032">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1033">
<b>L'analisi dei virus è disabilitata. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1034">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-1035">Antivirus Microsoft Defender la ricerca di virus è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1036">ID evento: 5100</span><span class="sxs-lookup"><span data-stu-id="d11b2-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-1037">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1039">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1040">
<b>La piattaforma antimalware scadrà a breve. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1041">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-1042">Antivirus Microsoft Defender è stato immesso un periodo di tolleranza e scadrà a breve.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="d11b2-1043">Dopo la scadenza, questo programma disabiliterà la protezione da virus, spyware e altro software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="d11b2-1044">
<dt>Motivo scadenza: motivo Antivirus Microsoft Defender scadenza.</dt> 
<dt>Data di scadenza: la data Antivirus Microsoft Defender scadrà.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1045">ID evento: 5101</span><span class="sxs-lookup"><span data-stu-id="d11b2-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="d11b2-1046">Nome simbolico:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1048">Messaggio:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="d11b2-1049">
<b>La piattaforma antimalware è scaduta. </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1050">Descrizione:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="d11b2-1051">Antivirus Microsoft Defender periodo di tolleranza è scaduto.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="d11b2-1052">La protezione da virus, spyware e altro software potenzialmente indesiderato è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="d11b2-1053">
<dt>Motivo scadenza:</dt>
<dt>data di scadenza: </dt>codice di 
<dt>errore: codice di errore Codice di &lt; risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="d11b2-1054">
</table>

<a id="error-codes"></a>
##Antivirus Microsoft Defender codici di errore client Se Antivirus Microsoft Defender si verificano problemi, in genere verrà visualizzato un codice di errore che consente di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="d11b2-1055">Molto spesso un errore indica che si è verificato un problema durante l'installazione di un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="d11b2-1056">In questa sezione vengono fornite le informazioni seguenti sugli errori Antivirus Microsoft Defender client.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="d11b2-1057">-   Il codice di -   errore Il possibile motivo dell'errore Consigli su cosa fare -   ora</span><span class="sxs-lookup"><span data-stu-id="d11b2-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="d11b2-1058">Utilizzare le informazioni contenute in queste tabelle per risolvere i Antivirus Microsoft Defender di errore.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1059">Codice di errore: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="d11b2-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="d11b2-1060">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1060">Message</span></span></td>
<td><span data-ttu-id="d11b2-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1062">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="d11b2-1063">Questo errore indica che la memoria potrebbe essere insufficiente.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="d11b2-1064">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="d11b2-1065">Controlla la memoria disponibile nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="d11b2-1066">Chiudi tutte le applicazioni inutilizzate in esecuzione per liberare memoria nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="d11b2-1067">Riavviare il dispositivo ed eseguire di nuovo l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1068">Codice di errore: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="d11b2-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="d11b2-1069">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1069">Message</span></span></td>
<td><span data-ttu-id="d11b2-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1071">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1072">Questo errore indica che potrebbe verificarsi un problema con il prodotto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="d11b2-1073">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="d11b2-1074">Aggiornare le definizioni.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1074">Update the definitions.</span></span> <span data-ttu-id="d11b2-1075">Uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11b2-1075">Either:</span></span><ol>
<li><span data-ttu-id="d11b2-1076">Fare clic <b>sul pulsante Aggiorna</b> definizioni nella <b>scheda</b> Aggiornamento in Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="d11b2-1077">Oppure</span><span class="sxs-lookup"><span data-stu-id="d11b2-1077">Or,</span></span>
</li>
<li><span data-ttu-id="d11b2-1078">Scaricare le definizioni più recenti <a href="https://aka.ms/wdsi">dal sito Intelligence di sicurezza Microsoft .</a></span><span class="sxs-lookup"><span data-stu-id="d11b2-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="d11b2-1079">Nota: le dimensioni del file di definizioni scaricato dal sito possono superare i 60 MB e non devono essere utilizzate come soluzione a lungo termine per l'aggiornamento delle definizioni.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="d11b2-1080">Eseguire un'analisi completa.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="d11b2-1081">Riavviare il dispositivo e riprovare.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1082">Codice di errore: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="d11b2-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="d11b2-1083">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1083">Message</span></span></td>
<td><span data-ttu-id="d11b2-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1085">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1086">Questo errore indica che potrebbe esserci un errore di configurazione del motore. In genere, ciò è correlato ai dati di input che non consentono al motore di funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1087">Codice di errore: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="d11b2-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1088">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1088">Message</span></span></td>
<td><span data-ttu-id="d11b2-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1090">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1091">Questo errore indica che non è Antivirus Microsoft Defender mettere in quarantena una minaccia.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1092">Codice di errore: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="d11b2-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1093">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1093">Message</span></span></td>
<td><span data-ttu-id="d11b2-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1095">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1096">Questo errore indica che è necessario un riavvio per completare la rimozione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="d11b2-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="d11b2-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1098">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1098">Message</span></span></td>
<td><span data-ttu-id="d11b2-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1100">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1101">Questo errore indica che la minaccia potrebbe non essere più presente nel supporto o che il malware potrebbe impedirti di analizzare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="d11b2-1102">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="d11b2-1103">Eseguire il <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> quindi aggiornare il software di sicurezza e riprovare.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1104">Codice di errore: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="d11b2-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="d11b2-1105">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1105">Message</span></span></td>
<td><span data-ttu-id="d11b2-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1107">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1108">Questo errore indica che potrebbe essere necessaria un'analisi completa del sistema.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="d11b2-1109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1109">Resolution</span></span></td><td>
<span data-ttu-id="d11b2-1110">Eseguire un'analisi completa del sistema.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1111">Codice di errore: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="d11b2-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1112">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1112">Message</span></span></td>
<td><span data-ttu-id="d11b2-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1114">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1115">Questo errore indica che sono necessari passaggi manuali per completare la rimozione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="d11b2-1116">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1116">Resolution</span></span></td><td>
<span data-ttu-id="d11b2-1117">Seguire la procedura di correzione manuale descritta <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">nell'enciclopedia Microsoft Malware Protection.</a></span><span class="sxs-lookup"><span data-stu-id="d11b2-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="d11b2-1118">È possibile trovare un collegamento specifico per le minacce nella cronologia degli eventi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1119">Codice di errore: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="d11b2-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1120">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1120">Message</span></span></td>
<td><span data-ttu-id="d11b2-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1122">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1123">Questo errore indica che la rimozione all'interno del tipo di contenitore potrebbe non essere supportata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="d11b2-1124">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1124">Resolution</span></span></td><td>
<span data-ttu-id="d11b2-1125">Antivirus Microsoft Defender non è in grado di correggere le minacce rilevate all'interno dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="d11b2-1126">Prendere in considerazione la rimozione manuale delle risorse rilevate.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1127">Codice di errore: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="d11b2-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1128">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1128">Message</span></span></td>
<td><span data-ttu-id="d11b2-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1130">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1131">Questo errore indica che la rimozione delle minacce di medie e medie dimensioni potrebbe essere disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="d11b2-1132">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1132">Resolution</span></span></td><td>
<span data-ttu-id="d11b2-1133">Controllare le minacce rilevate e risolverle in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1134">Codice di errore: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="d11b2-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1135">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1135">Message</span></span></td>
<td><span data-ttu-id="d11b2-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1137">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1138">Questo errore indica che è necessaria una nuova analisi della minaccia.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="d11b2-1139">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1139">Resolution</span></span></td><td>
<span data-ttu-id="d11b2-1140">Eseguire un'analisi completa del sistema.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1141">Codice di errore: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="d11b2-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1142">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1142">Message</span></span></td>
<td><span data-ttu-id="d11b2-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="d11b2-1144">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1145">Questo errore indica che è necessaria un'analisi offline.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="d11b2-1146">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1146">Resolution</span></span></td><td>
<span data-ttu-id="d11b2-1147">Esegui offline Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="d11b2-1148">Per informazioni su come eseguire questa operazione, vedere <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">l'articolo offline Antivirus Microsoft Defender .</a></span><span class="sxs-lookup"><span data-stu-id="d11b2-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="d11b2-1149">Codice di errore: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="d11b2-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="d11b2-1150">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d11b2-1150">Message</span></span></td>
<td><span data-ttu-id="d11b2-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="d11b2-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="d11b2-1152">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="d11b2-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="d11b2-1153">Questo errore indica che Antivirus Microsoft Defender non supporta la versione corrente della piattaforma e richiede una nuova versione della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="d11b2-1154">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1154">Resolution</span></span></td><td>
<span data-ttu-id="d11b2-1155">È possibile utilizzare solo Antivirus Microsoft Defender in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="d11b2-1156">Ad Windows 8, Windows 7 e Windows Vista, è possibile utilizzare <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="d11b2-1157">

<a id="internal-error-codes"></a>I codici di errore seguenti vengono utilizzati durante i test interni di Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="d11b2-1158">Se vengono visualizzati questi errori, puoi provare ad [aggiornare](manage-updates-baselines-microsoft-defender-antivirus.md) le definizioni e forzare una nuova analisi direttamente nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="d11b2-1159">Codici di errore interni</span><span class="sxs-lookup"><span data-stu-id="d11b2-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d11b2-1160"><b>Codice di errore</b></span><span class="sxs-lookup"><span data-stu-id="d11b2-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="d11b2-1161">Messaggio visualizzato</span><span class="sxs-lookup"><span data-stu-id="d11b2-1161">Message displayed</span></span></th>
<th><span data-ttu-id="d11b2-1162">Possibile motivo dell'errore e della risoluzione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="d11b2-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="d11b2-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="d11b2-1165">Controllare la connessione Internet, quindi eseguire di nuovo l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="d11b2-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="d11b2-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="d11b2-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="d11b2-1168">Si tratta di un errore interno.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1168">This is an internal error.</span></span> <span data-ttu-id="d11b2-1169">La causa non è chiaramente definita.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="d11b2-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="d11b2-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="d11b2-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="d11b2-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="d11b2-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="d11b2-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="d11b2-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="d11b2-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="d11b2-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="d11b2-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="d11b2-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="d11b2-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="d11b2-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="d11b2-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="d11b2-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="d11b2-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="d11b2-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="d11b2-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="d11b2-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="d11b2-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="d11b2-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="d11b2-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="d11b2-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="d11b2-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="d11b2-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="d11b2-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="d11b2-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="d11b2-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="d11b2-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="d11b2-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="d11b2-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="d11b2-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="d11b2-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="d11b2-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="d11b2-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="d11b2-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="d11b2-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="d11b2-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="d11b2-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="d11b2-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="d11b2-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="d11b2-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="d11b2-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="d11b2-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="d11b2-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="d11b2-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="d11b2-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="d11b2-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="d11b2-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="d11b2-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="d11b2-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="d11b2-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="d11b2-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="d11b2-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="d11b2-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="d11b2-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="d11b2-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="d11b2-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="d11b2-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="d11b2-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="d11b2-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="d11b2-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="d11b2-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="d11b2-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="d11b2-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="d11b2-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="d11b2-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="d11b2-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="d11b2-1238">Si tratta di un errore interno.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1238">This is an internal error.</span></span> <span data-ttu-id="d11b2-1239">Potrebbe essere attivato quando la rimozione malware non riesce.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="d11b2-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="d11b2-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="d11b2-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="d11b2-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="d11b2-1242">Si tratta di un errore interno.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1242">This is an internal error.</span></span> <span data-ttu-id="d11b2-1243">Potrebbe essere stato attivato quando un'analisi non viene completata.</span><span class="sxs-lookup"><span data-stu-id="d11b2-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="d11b2-1244">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d11b2-1244">Related topics</span></span>

- [<span data-ttu-id="d11b2-1245">Report sulla Antivirus Microsoft Defender protezione</span><span class="sxs-lookup"><span data-stu-id="d11b2-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d11b2-1246">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="d11b2-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)