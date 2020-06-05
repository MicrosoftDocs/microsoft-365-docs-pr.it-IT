---
title: Utilizzare la ricerca contenuto per cercare i dati importati di terze parti
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
description: Utilizzare lo strumento eDiscovery ricerca contenuto per cercare gli elementi importati nelle cassette postali in Microsoft 365 da un'origine dati di terze parti. È possibile creare una query per cercare tutti gli elementi importati o creare una query per la ricerca di tipi di dati specifici di terze parti. In questo articolo vengono elencati i valori che è possibile utilizzare in una query di parole chiave per eseguire la ricerca nei tipi di dati di terze parti che è possibile importare in Microsoft 365.
ms.openlocfilehash: c494f4bbb13919f9a980f227093d291c148e9afe
ms.sourcegitcommit: 86705d15231c987be2fcf5a295b9b6239fc46077
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "44566670"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="37d89-105">Utilizzare la ricerca contenuto per eseguire la ricerca di dati di terze parti importati da un connettore partner personalizzato</span><span class="sxs-lookup"><span data-stu-id="37d89-105">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="37d89-106">È possibile utilizzare lo [strumento eDiscovery ricerca contenuto](content-search.md) nel centro sicurezza & Compliance per cercare gli elementi importati nelle cassette postali in Microsoft 365 da un'origine dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="37d89-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="37d89-107">È possibile creare una query per eseguire una ricerca in tutti gli elementi di dati di terze parti importati oppure creare una query per la ricerca di elementi di dati di terze parti specifici.</span><span class="sxs-lookup"><span data-stu-id="37d89-107">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="37d89-108">Inoltre, è anche possibile creare un criterio di conservazione basato su query o un blocco di eDiscovery basato su query per conservare i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="37d89-108">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="37d89-109">Per ulteriori informazioni sull'utilizzo di un partner per l'importazione di dati di terze parti e un elenco dei tipi di dati di terze parti che è possibile importare in Microsoft 365, vedere [collaborare con un partner per archiviare i dati di terze parti in Office 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="37d89-109">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37d89-110">Le indicazioni contenute in questo articolo si applicano solo ai dati di terze parti che sono stati importati da un connettore partner personalizzato.</span><span class="sxs-lookup"><span data-stu-id="37d89-110">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="37d89-111">Questo articolo non si applica ai dati di terze parti che vengono importati utilizzando i [connettori di dati di terze parti](archiving-third-party-data.md#third-party-data-connectors) nel centro conformità Microsoft.</span><span class="sxs-lookup"><span data-stu-id="37d89-111">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="37d89-112">Creazione di una query per la ricerca di tutti i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="37d89-112">Creating a query to search all third-party data</span></span>

<span data-ttu-id="37d89-113">Per cercare (o inserire un blocco) qualsiasi tipo di dati di terze parti importati in Office 365, è possibile utilizzare la `kind:externaldata` coppia proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto o durante la creazione di un blocco basato su query.</span><span class="sxs-lookup"><span data-stu-id="37d89-113">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="37d89-114">Ad esempio, per cercare gli elementi importati da un'origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="37d89-114">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="37d89-115">Nell'esempio di query con parole chiave precedenti è inclusa la proprietà Subject.</span><span class="sxs-lookup"><span data-stu-id="37d89-115">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="37d89-116">Per un elenco di altre proprietà per gli elementi di dati di terze parti che possono essere inclusi in una query di parole chiave, vedere la sezione "ulteriori informazioni" in [collaborazione con un partner per archiviare i dati di terze parti in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="37d89-116">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="37d89-117">Quando si creano query per la ricerca e la conservazione dei dati di terze parti, è anche possibile utilizzare le condizioni per limitare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="37d89-117">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="37d89-118">Per ulteriori informazioni sulla creazione di query di ricerca del contenuto, vedere [keyword query and Search Conditions for content search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="37d89-118">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="37d89-119">Creazione di una query per la ricerca di tipi specifici di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="37d89-119">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="37d89-120">Anziché cercare tutti i tipi di dati di terze parti, è possibile creare query che cercano solo un tipo di dati di terze parti tramite la seguente coppia di *proprietà del messaggio: valore* nella casella parola chiave per una ricerca contenuto:</span><span class="sxs-lookup"><span data-stu-id="37d89-120">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="37d89-121">Ad esempio, per cercare i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="37d89-121">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="37d89-122">Nella tabella seguente sono elencati i tipi di dati di terze parti di cui è possibile eseguire la ricerca e il valore da utilizzare per la `itemclass:` Proprietà Message per cercare in modo specifico il tipo di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="37d89-122">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="37d89-123">La sintassi della query non è distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="37d89-123">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="37d89-124">**Tipo di dati di terze parti**</span><span class="sxs-lookup"><span data-stu-id="37d89-124">**Third-party data type**</span></span>|<span data-ttu-id="37d89-125">**Valore della `itemclass:` Proprietà**</span><span class="sxs-lookup"><span data-stu-id="37d89-125">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="37d89-126">OBIETTIVO</span><span class="sxs-lookup"><span data-stu-id="37d89-126">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="37d89-127">American Idol</span><span class="sxs-lookup"><span data-stu-id="37d89-127">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="37d89-128">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="37d89-128">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="37d89-129">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="37d89-129">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="37d89-130">Ares</span><span class="sxs-lookup"><span data-stu-id="37d89-130">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="37d89-131">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="37d89-131">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="37d89-132">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="37d89-132">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="37d89-133">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="37d89-133">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="37d89-134">Segnaposto AXS</span><span class="sxs-lookup"><span data-stu-id="37d89-134">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="37d89-135">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="37d89-135">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="37d89-136">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="37d89-136">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="37d89-137">BearShare</span><span class="sxs-lookup"><span data-stu-id="37d89-137">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="37d89-138">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="37d89-138">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="37d89-139">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="37d89-139">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="37d89-140">Registri chiamate BlackBerry</span><span class="sxs-lookup"><span data-stu-id="37d89-140">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="37d89-141">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="37d89-141">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="37d89-142">PIN BlackBerry</span><span class="sxs-lookup"><span data-stu-id="37d89-142">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="37d89-143">SMS BlackBerry</span><span class="sxs-lookup"><span data-stu-id="37d89-143">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="37d89-144">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="37d89-144">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="37d89-145">Posta Bloomberg</span><span class="sxs-lookup"><span data-stu-id="37d89-145">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="37d89-146">Messaggistica Bloomberg</span><span class="sxs-lookup"><span data-stu-id="37d89-146">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="37d89-147">Box</span><span class="sxs-lookup"><span data-stu-id="37d89-147">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="37d89-148">Server di presenza di messaggistica istantanea Cisco &amp;</span><span class="sxs-lookup"><span data-stu-id="37d89-148">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="37d89-149">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="37d89-149">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="37d89-150">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="37d89-150">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="37d89-151">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="37d89-151">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="37d89-152">Facebook</span><span class="sxs-lookup"><span data-stu-id="37d89-152">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="37d89-153">FastTrack</span><span class="sxs-lookup"><span data-stu-id="37d89-153">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="37d89-154">FXConnect</span><span class="sxs-lookup"><span data-stu-id="37d89-154">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="37d89-155">Flickr</span><span class="sxs-lookup"><span data-stu-id="37d89-155">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="37d89-156">Gnutella</span><span class="sxs-lookup"><span data-stu-id="37d89-156">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="37d89-157">Google +</span><span class="sxs-lookup"><span data-stu-id="37d89-157">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="37d89-158">Google Talk</span><span class="sxs-lookup"><span data-stu-id="37d89-158">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="37d89-159">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="37d89-159">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="37d89-160">HipChat</span><span class="sxs-lookup"><span data-stu-id="37d89-160">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="37d89-161">Hopster</span><span class="sxs-lookup"><span data-stu-id="37d89-161">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="37d89-162">HubConnex</span><span class="sxs-lookup"><span data-stu-id="37d89-162">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="37d89-163">Connessioni IBM</span><span class="sxs-lookup"><span data-stu-id="37d89-163">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="37d89-164">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="37d89-164">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="37d89-165">Chat di ghiaccio</span><span class="sxs-lookup"><span data-stu-id="37d89-165">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="37d89-166">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="37d89-166">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="37d89-167">Instagram</span><span class="sxs-lookup"><span data-stu-id="37d89-167">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="37d89-168">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="37d89-168">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="37d89-169">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="37d89-169">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="37d89-170">IRC</span><span class="sxs-lookup"><span data-stu-id="37d89-170">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="37d89-171">Jive</span><span class="sxs-lookup"><span data-stu-id="37d89-171">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="37d89-172">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="37d89-172">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="37d89-173">JXTA</span><span class="sxs-lookup"><span data-stu-id="37d89-173">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="37d89-174">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="37d89-174">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="37d89-175">MFTP</span><span class="sxs-lookup"><span data-stu-id="37d89-175">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="37d89-176">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="37d89-176">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="37d89-177">Allinea mente</span><span class="sxs-lookup"><span data-stu-id="37d89-177">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="37d89-178">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="37d89-178">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="37d89-179">MSN</span><span class="sxs-lookup"><span data-stu-id="37d89-179">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="37d89-180">MySpace</span><span class="sxs-lookup"><span data-stu-id="37d89-180">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="37d89-181">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="37d89-181">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="37d89-182">OpenNap</span><span class="sxs-lookup"><span data-stu-id="37d89-182">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="37d89-183">Pinterest</span><span class="sxs-lookup"><span data-stu-id="37d89-183">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="37d89-184">Pivot</span><span class="sxs-lookup"><span data-stu-id="37d89-184">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="37d89-185">QQ</span><span class="sxs-lookup"><span data-stu-id="37d89-185">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="37d89-186">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="37d89-186">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="37d89-187">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="37d89-187">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="37d89-188">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="37d89-188">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="37d89-189">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="37d89-189">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="37d89-190">SoftEther</span><span class="sxs-lookup"><span data-stu-id="37d89-190">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="37d89-191">Squawker</span><span class="sxs-lookup"><span data-stu-id="37d89-191">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="37d89-192">Sinfonia</span><span class="sxs-lookup"><span data-stu-id="37d89-192">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="37d89-193">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="37d89-193">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="37d89-194">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="37d89-194">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="37d89-195">Tor</span><span class="sxs-lookup"><span data-stu-id="37d89-195">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="37d89-196">TTT</span><span class="sxs-lookup"><span data-stu-id="37d89-196">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="37d89-197">Twitter</span><span class="sxs-lookup"><span data-stu-id="37d89-197">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="37d89-198">Chat UBS</span><span class="sxs-lookup"><span data-stu-id="37d89-198">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="37d89-199">Officemix</span><span class="sxs-lookup"><span data-stu-id="37d89-199">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="37d89-200">WinMX</span><span class="sxs-lookup"><span data-stu-id="37d89-200">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="37d89-201">Winny</span><span class="sxs-lookup"><span data-stu-id="37d89-201">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="37d89-202">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="37d89-202">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="37d89-203">Yammer</span><span class="sxs-lookup"><span data-stu-id="37d89-203">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="37d89-204">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="37d89-204">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="37d89-205">YouTube</span><span class="sxs-lookup"><span data-stu-id="37d89-205">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
