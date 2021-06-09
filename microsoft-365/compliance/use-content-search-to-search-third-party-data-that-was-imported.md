---
title: Utilizzare Ricerca contenuto per cercare dati importati di terze parti
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Utilizzare lo strumento eDiscovery ricerca contenuto per cercare gli elementi importati nelle cassette postali in Microsoft 365 da un'origine dati di terze parti creando query.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324572"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="44bde-103">Utilizzare Ricerca contenuto per cercare dati di terze parti importati da un connettore partner personalizzato</span><span class="sxs-lookup"><span data-stu-id="44bde-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="44bde-104">È possibile utilizzare lo strumento Ricerca contenuto [eDiscovery](content-search.md) nel Centro sicurezza & conformità per cercare gli elementi importati nelle cassette postali in Microsoft 365 da un'origine dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="44bde-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="44bde-105">È possibile creare una query per cercare tutti gli elementi di dati di terze parti importati oppure creare una query per cercare elementi di dati di terze parti specifici.</span><span class="sxs-lookup"><span data-stu-id="44bde-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="44bde-106">È inoltre possibile creare criteri di conservazione basati su query o un blocco eDiscovery basato su query per conservare i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="44bde-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="44bde-107">Per ulteriori informazioni sull'utilizzo di un partner per importare dati di terze parti e un elenco dei tipi di dati di terze parti che è possibile importare in Microsoft 365, vedere Collaborare con un partner per archiviare dati di terze parti [in Office 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="44bde-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44bde-108">Le indicazioni fornite in questo articolo si applicano solo ai dati di terze parti importati da un connettore partner personalizzato.</span><span class="sxs-lookup"><span data-stu-id="44bde-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="44bde-109">Questo articolo non si applica ai dati di terze parti importati tramite i connettori di [dati](archiving-third-party-data.md#third-party-data-connectors) di terze parti nel Centro conformità Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44bde-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="44bde-110">Creazione di una query per cercare tutti i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="44bde-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="44bde-111">Per cercare (o mettere in attesa) qualsiasi tipo di dati di terze parti importati in Office 365, è possibile utilizzare la coppia proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto o quando si crea un'esenzione basata su `kind:externaldata` query.</span><span class="sxs-lookup"><span data-stu-id="44bde-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="44bde-112">Ad esempio, per cercare gli elementi importati da qualsiasi origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="44bde-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="44bde-113">L'esempio di query con parole chiave precedente include la proprietà subject.</span><span class="sxs-lookup"><span data-stu-id="44bde-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="44bde-114">Per un elenco di altre proprietà per elementi di dati di terze parti che possono includere in una query con parole chiave, vedere la sezione "Ulteriori informazioni" in Collaborare con un partner per archiviare dati di terze parti [in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="44bde-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="44bde-115">Quando si creano query per cercare e contenere dati di terze parti, è inoltre possibile utilizzare le condizioni per restringere i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="44bde-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="44bde-116">Per ulteriori informazioni sulla creazione di query di ricerca contenuto, vedere Query con parole chiave e condizioni [di ricerca per Ricerca contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="44bde-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="44bde-117">Creazione di una query per la ricerca di tipi specifici di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="44bde-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="44bde-118">Anziché cercare tutti i tipi di dati di terze parti, è possibile creare query che cercano solo un tipo specifico di dati di terze parti utilizzando la proprietà messaggio *seguente:* coppia valore nella casella parola chiave per una ricerca contenuto:</span><span class="sxs-lookup"><span data-stu-id="44bde-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="44bde-119">Ad esempio, per cercare i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="44bde-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="44bde-120">Nella tabella seguente sono elencati i tipi di dati di terze parti che è possibile cercare e il valore da utilizzare per la proprietà del messaggio per cercare in modo specifico tale tipo di  `itemclass:` dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="44bde-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="44bde-121">La sintassi della query non fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="44bde-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="44bde-122">**Tipo di dati di terze parti**</span><span class="sxs-lookup"><span data-stu-id="44bde-122">**Third-party data type**</span></span>|<span data-ttu-id="44bde-123">**Valore per  `itemclass:` la proprietà**</span><span class="sxs-lookup"><span data-stu-id="44bde-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44bde-124">AIM</span><span class="sxs-lookup"><span data-stu-id="44bde-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="44bde-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="44bde-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="44bde-126">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="44bde-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="44bde-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="44bde-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="44bde-128">Ares</span><span class="sxs-lookup"><span data-stu-id="44bde-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="44bde-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="44bde-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="44bde-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="44bde-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="44bde-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="44bde-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="44bde-132">Segnaposto assi</span><span class="sxs-lookup"><span data-stu-id="44bde-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="44bde-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="44bde-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="44bde-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="44bde-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="44bde-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="44bde-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="44bde-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="44bde-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="44bde-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="44bde-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="44bde-138">Log delle chiamate BlackBerry</span><span class="sxs-lookup"><span data-stu-id="44bde-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="44bde-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="44bde-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="44bde-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="44bde-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="44bde-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="44bde-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="44bde-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="44bde-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="44bde-143">Bloomberg Message</span><span class="sxs-lookup"><span data-stu-id="44bde-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="44bde-144">Messaggistica Bloomberg</span><span class="sxs-lookup"><span data-stu-id="44bde-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="44bde-145">Box</span><span class="sxs-lookup"><span data-stu-id="44bde-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="44bde-146">Server presenza messaggistica istantanea Cisco &amp;</span><span class="sxs-lookup"><span data-stu-id="44bde-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="44bde-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="44bde-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="44bde-148">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="44bde-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="44bde-149">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="44bde-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="44bde-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="44bde-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="44bde-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="44bde-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="44bde-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="44bde-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="44bde-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="44bde-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="44bde-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="44bde-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="44bde-155">Google+</span><span class="sxs-lookup"><span data-stu-id="44bde-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="44bde-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="44bde-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="44bde-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="44bde-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="44bde-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="44bde-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="44bde-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="44bde-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="44bde-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="44bde-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="44bde-161">IBM Connections</span><span class="sxs-lookup"><span data-stu-id="44bde-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="44bde-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="44bde-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="44bde-163">ICE Chat</span><span class="sxs-lookup"><span data-stu-id="44bde-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="44bde-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="44bde-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="44bde-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="44bde-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="44bde-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="44bde-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="44bde-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="44bde-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="44bde-168">IRC</span><span class="sxs-lookup"><span data-stu-id="44bde-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="44bde-169">Jive</span><span class="sxs-lookup"><span data-stu-id="44bde-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="44bde-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="44bde-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="44bde-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="44bde-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="44bde-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="44bde-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="44bde-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="44bde-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="44bde-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="44bde-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="44bde-175">Mind Align</span><span class="sxs-lookup"><span data-stu-id="44bde-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="44bde-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="44bde-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="44bde-177">MSN</span><span class="sxs-lookup"><span data-stu-id="44bde-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="44bde-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="44bde-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="44bde-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="44bde-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="44bde-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="44bde-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="44bde-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="44bde-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="44bde-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="44bde-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="44bde-183">QQ</span><span class="sxs-lookup"><span data-stu-id="44bde-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="44bde-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="44bde-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="44bde-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="44bde-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="44bde-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="44bde-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="44bde-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="44bde-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="44bde-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="44bde-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="44bde-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="44bde-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="44bde-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="44bde-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="44bde-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="44bde-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="44bde-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="44bde-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="44bde-193">Tor</span><span class="sxs-lookup"><span data-stu-id="44bde-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="44bde-194">TTT</span><span class="sxs-lookup"><span data-stu-id="44bde-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="44bde-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="44bde-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="44bde-196">Chat UBS</span><span class="sxs-lookup"><span data-stu-id="44bde-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="44bde-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="44bde-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="44bde-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="44bde-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="44bde-199">Winny</span><span class="sxs-lookup"><span data-stu-id="44bde-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="44bde-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="44bde-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="44bde-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="44bde-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="44bde-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="44bde-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="44bde-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="44bde-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
