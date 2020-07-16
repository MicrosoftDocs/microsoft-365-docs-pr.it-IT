---
title: Collaborare con un partner per archiviare i dati di terze parti
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come configurare un connettore personalizzato per l'importazione di dati di terze parti da origini dati quali Salesforce Chatter, Yahoo Messenger o Yammer.
ms.openlocfilehash: c3b824909ae1243e2dd1f12b799e53d00d9615ca
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126655"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="e57ef-103">Collaborare con un partner per archiviare i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e57ef-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="e57ef-104">È possibile collaborare con un partner Microsoft per importare e archiviare i dati da un'origine dati di terze parti a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="e57ef-105">Un partner può fornire un connettore personalizzato configurato per estrarre elementi dall'origine dati di terze parti (su base regolare) e quindi importare tali elementi.</span><span class="sxs-lookup"><span data-stu-id="e57ef-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="e57ef-106">Il connettore partner converte il contenuto di un elemento dall'origine dati in un formato di messaggio di posta elettronica e quindi archivia gli elementi nelle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="e57ef-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="e57ef-107">Dopo l'importazione di dati di terze parti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, la ricerca del contenuto, l'archiviazione sul posto, il controllo e i criteri di conservazione di Microsoft 365 a questi dati.</span><span class="sxs-lookup"><span data-stu-id="e57ef-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>
  
<span data-ttu-id="e57ef-108">Di seguito è riportata una panoramica del processo e dei passaggi necessari per l'utilizzo di un partner Microsoft per l'importazione di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-108">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="e57ef-109">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="e57ef-109">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="e57ef-110">Passaggio 2: creare e configurare una cassetta postale di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e57ef-110">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="e57ef-111">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="e57ef-111">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="e57ef-112">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="e57ef-112">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="e57ef-113">Passaggio 5: registrare il connettore di dati di terze parti in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e57ef-113">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="e57ef-114">Funzionamento del processo di importazione dei dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e57ef-114">How the third-party data import process works</span></span>

<span data-ttu-id="e57ef-115">Nella figura e nella descrizione seguenti viene illustrato il funzionamento del processo di importazione di dati di terze parti quando si lavora con un partner.</span><span class="sxs-lookup"><span data-stu-id="e57ef-115">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Funzionamento del processo di importazione dei dati di terze parti](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="e57ef-117">Il cliente collabora con il proprio partner preferito per configurare un connettore che estrae gli elementi dall'origine dati di terze parti e quindi importa tali elementi in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-117">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="e57ef-118">Il connettore partner si connette a origini dati di terze parti tramite un'API di terze parti (su base pianificata o configurata) ed estrae gli elementi dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e57ef-118">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="e57ef-119">Il connettore partner converte il contenuto di un elemento in un formato di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e57ef-119">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="e57ef-120">Vedere la sezione [ulteriori informazioni](#more-information) per una descrizione dello schema del formato dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="e57ef-120">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="e57ef-121">Il connettore partner si connette al servizio di Azure in Microsoft 365 utilizzando il servizio Web Exchange (EWS) tramite un punto finale noto.</span><span class="sxs-lookup"><span data-stu-id="e57ef-121">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="e57ef-p103">Gli elementi vengono importati nella cassetta postale di un utente specifico oppure in una cassetta postale generale di dati di terze parti. Il fatto che un elemento sia importato nella cassetta postale di un utente specifico o nella cassetta postale di dati di terze parti dipende dai seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="e57ef-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="e57ef-124">**Elementi che dispongono di un ID utente corrispondente a un account utente:** Se il connettore partner è in grado di eseguire il mapping dell'ID utente dell'elemento nell'origine dati di terze parti a un ID utente specifico in Office 365, l'elemento viene copiato nella cartella **Purges** nella cartella elementi ripristinabili dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e57ef-124">**Items that have a user ID that corresponds to an user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="e57ef-125">Gli utenti non possono accedere agli elementi nella cartella Ripuliture.</span><span class="sxs-lookup"><span data-stu-id="e57ef-125">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="e57ef-126">Tuttavia, è possibile utilizzare gli strumenti di eDiscovery per cercare gli elementi nella cartella Purges.</span><span class="sxs-lookup"><span data-stu-id="e57ef-126">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="e57ef-127">**Elementi che non dispongono di un ID utente corrispondente a un account utente:** Se il connettore partner non è in grado di mappare l'ID utente di un elemento a uno specifico ID utente, l'elemento viene copiato nella cartella **posta in arrivo** della cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-127">**Items that don't have a user ID that corresponds to an user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="e57ef-128">L'importazione di elementi nella posta in arrivo consente a un utente dell'organizzazione di accedere alla cassetta postale di terze parti per visualizzare e gestire questi elementi e vedere se è necessario prevedere modifiche nella configurazione del connettore partner.</span><span class="sxs-lookup"><span data-stu-id="e57ef-128">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="e57ef-129">Passaggio 1: trovare un partner di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e57ef-129">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="e57ef-130">Un componente chiave per l'archiviazione dei dati di terze parti in Microsoft 365 è l'individuazione e l'utilizzo di un partner Microsoft specializzato nell'acquisizione dei dati da un'origine dati di terze parti e nell'importazione in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-130">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="e57ef-131">Dopo aver importato i dati, è possibile archiviarli e conservarli insieme agli altri dati di Microsoft dell'organizzazione, ad esempio la posta elettronica da Exchange e i documenti di SharePoint e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="e57ef-131">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="e57ef-132">Un partner crea un connettore che estrae i dati dalle origini dati di terze parti dell'organizzazione (ad esempio, BlackBerry, Facebook, Google +, Thomson Reuters, Twitter e YouTube) e passa tali dati a un'API di Office 365 che importa gli elementi nelle cassette postali di Exchange come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e57ef-132">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="e57ef-133">Nelle sezioni seguenti vengono elencati i partner Microsoft e le origini dati di terze parti che supportano, che partecipano al programma per l'archiviazione dei dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-133">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="e57ef-134">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="e57ef-134">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="e57ef-135">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="e57ef-135">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="e57ef-136">Globanet</span><span class="sxs-lookup"><span data-stu-id="e57ef-136">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="e57ef-137">OpenText</span><span class="sxs-lookup"><span data-stu-id="e57ef-137">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="e57ef-138">Smarsh</span><span class="sxs-lookup"><span data-stu-id="e57ef-138">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="e57ef-139">Verba</span><span class="sxs-lookup"><span data-stu-id="e57ef-139">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="e57ef-140">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="e57ef-140">17a-4 LLC</span></span>

<span data-ttu-id="e57ef-141">[17a-4 LLC](https://www.17a-4.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-141">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="e57ef-142">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="e57ef-142">BlackBerry</span></span>
    
- <span data-ttu-id="e57ef-143">Flussi di dati di Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e57ef-143">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="e57ef-144">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="e57ef-144">Cisco Jabber</span></span>
    
- <span data-ttu-id="e57ef-145">Factt</span><span class="sxs-lookup"><span data-stu-id="e57ef-145">FactSet</span></span>
    
- <span data-ttu-id="e57ef-146">HipChat</span><span class="sxs-lookup"><span data-stu-id="e57ef-146">HipChat</span></span>
    
- <span data-ttu-id="e57ef-147">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="e57ef-147">InvestEdge</span></span>
    
- <span data-ttu-id="e57ef-148">LivePerson</span><span class="sxs-lookup"><span data-stu-id="e57ef-148">LivePerson</span></span>
    
- <span data-ttu-id="e57ef-149">Flussi di dati MessageLabs</span><span class="sxs-lookup"><span data-stu-id="e57ef-149">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="e57ef-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="e57ef-150">OpenText</span></span>
    
- <span data-ttu-id="e57ef-151">Guida "click-to-call" di Oracle/ATG</span><span class="sxs-lookup"><span data-stu-id="e57ef-151">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="e57ef-152">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="e57ef-152">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="e57ef-153">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="e57ef-153">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="e57ef-154">MindAlign</span><span class="sxs-lookup"><span data-stu-id="e57ef-154">MindAlign</span></span>
    
- <span data-ttu-id="e57ef-155">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="e57ef-155">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="e57ef-156">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="e57ef-156">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="e57ef-157">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="e57ef-157">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="e57ef-158">Database SQL</span><span class="sxs-lookup"><span data-stu-id="e57ef-158">SQL Databases</span></span>
    
- <span data-ttu-id="e57ef-159">Squawker</span><span class="sxs-lookup"><span data-stu-id="e57ef-159">Squawker</span></span>
    
- <span data-ttu-id="e57ef-160">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="e57ef-160">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="e57ef-161">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="e57ef-161">ArchiveSocial</span></span>

<span data-ttu-id="e57ef-162">[ArchiveSocial](https://www.archivesocial.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-162">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e57ef-163">Facebook</span><span class="sxs-lookup"><span data-stu-id="e57ef-163">Facebook</span></span>
    
- <span data-ttu-id="e57ef-164">Flickr</span><span class="sxs-lookup"><span data-stu-id="e57ef-164">Flickr</span></span>
    
- <span data-ttu-id="e57ef-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="e57ef-165">Instagram</span></span>
    
- <span data-ttu-id="e57ef-166">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e57ef-166">LinkedIn</span></span>
    
- <span data-ttu-id="e57ef-167">Pinterest</span><span class="sxs-lookup"><span data-stu-id="e57ef-167">Pinterest</span></span>
    
- <span data-ttu-id="e57ef-168">Twitter</span><span class="sxs-lookup"><span data-stu-id="e57ef-168">Twitter</span></span>
    
- <span data-ttu-id="e57ef-169">YouTube</span><span class="sxs-lookup"><span data-stu-id="e57ef-169">YouTube</span></span>
    
- <span data-ttu-id="e57ef-170">Officemix</span><span class="sxs-lookup"><span data-stu-id="e57ef-170">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="e57ef-171">Globanet</span><span class="sxs-lookup"><span data-stu-id="e57ef-171">Globanet</span></span>

<span data-ttu-id="e57ef-172">[Globanet](https://www.globanet.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-172">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e57ef-173">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="e57ef-173">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="e57ef-174">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e57ef-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e57ef-175">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e57ef-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e57ef-176">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e57ef-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e57ef-177">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e57ef-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e57ef-178">Chat Bloomber</span><span class="sxs-lookup"><span data-stu-id="e57ef-178">Bloomberg Chat</span></span>
    
- <span data-ttu-id="e57ef-179">Posta Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e57ef-179">Bloomberg Mail</span></span>
    
- <span data-ttu-id="e57ef-180">Box</span><span class="sxs-lookup"><span data-stu-id="e57ef-180">Box</span></span>
    
- <span data-ttu-id="e57ef-181">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e57ef-181">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="e57ef-182">Server di presenza di messaggistica istantanea Cisco &amp; (V10, v 10.5.1 su1, v 11.0, v 11,5 SU2)</span><span class="sxs-lookup"><span data-stu-id="e57ef-182">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="e57ef-183">Team Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="e57ef-183">Cisco Webex Teams</span></span>

- <span data-ttu-id="e57ef-184">ShareFile di area di lavoro Citrix &amp;</span><span class="sxs-lookup"><span data-stu-id="e57ef-184">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="e57ef-185">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="e57ef-185">CrowdCompass</span></span>

- <span data-ttu-id="e57ef-186">File di testo con valori delimitati da personalizzato</span><span class="sxs-lookup"><span data-stu-id="e57ef-186">Custom-delimited text files</span></span>
    
- <span data-ttu-id="e57ef-187">File XML personalizzati</span><span class="sxs-lookup"><span data-stu-id="e57ef-187">Custom XML files</span></span>
    
- <span data-ttu-id="e57ef-188">Facebook (pagine)</span><span class="sxs-lookup"><span data-stu-id="e57ef-188">Facebook (Pages)</span></span>
    
- <span data-ttu-id="e57ef-189">Factt</span><span class="sxs-lookup"><span data-stu-id="e57ef-189">Factset</span></span>
    
- <span data-ttu-id="e57ef-190">FXConnect</span><span class="sxs-lookup"><span data-stu-id="e57ef-190">FXConnect</span></span>
    
- <span data-ttu-id="e57ef-191">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e57ef-191">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="e57ef-192">Jive</span><span class="sxs-lookup"><span data-stu-id="e57ef-192">Jive</span></span>
    
- <span data-ttu-id="e57ef-193">XIP Macgregor</span><span class="sxs-lookup"><span data-stu-id="e57ef-193">Macgregor XIP</span></span>

- <span data-ttu-id="e57ef-194">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e57ef-194">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="e57ef-195">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e57ef-195">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="e57ef-196">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e57ef-196">Microsoft Teams</span></span>
       
- <span data-ttu-id="e57ef-197">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="e57ef-197">Microsoft Yammer</span></span>
    
- <span data-ttu-id="e57ef-198">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="e57ef-198">Mobile Guard</span></span>
    
- <span data-ttu-id="e57ef-199">Pivot</span><span class="sxs-lookup"><span data-stu-id="e57ef-199">Pivot</span></span>
    
- <span data-ttu-id="e57ef-200">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="e57ef-200">Salesforce Chatter</span></span>

- <span data-ttu-id="e57ef-201">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e57ef-201">Skype for Business Online</span></span>
    
- <span data-ttu-id="e57ef-202">Skype for Business, versioni 2007 R2 - 2016 (locale)</span><span class="sxs-lookup"><span data-stu-id="e57ef-202">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="e57ef-203">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="e57ef-203">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="e57ef-204">Sinfonia</span><span class="sxs-lookup"><span data-stu-id="e57ef-204">Symphony</span></span>
    
- <span data-ttu-id="e57ef-205">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="e57ef-205">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="e57ef-206">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="e57ef-206">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="e57ef-207">Thomson Reuters Dealings 3000/FX Trading</span><span class="sxs-lookup"><span data-stu-id="e57ef-207">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="e57ef-208">Twitter</span><span class="sxs-lookup"><span data-stu-id="e57ef-208">Twitter</span></span>
    
- <span data-ttu-id="e57ef-209">Chat UBS</span><span class="sxs-lookup"><span data-stu-id="e57ef-209">UBS Chat</span></span>
    
- <span data-ttu-id="e57ef-210">YouTube</span><span class="sxs-lookup"><span data-stu-id="e57ef-210">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="e57ef-211">OpenText</span><span class="sxs-lookup"><span data-stu-id="e57ef-211">OpenText</span></span>

<span data-ttu-id="e57ef-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e57ef-213">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="e57ef-213">Axs Encrypted</span></span>
    
- <span data-ttu-id="e57ef-214">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="e57ef-214">Axs Exchange</span></span>
    
- <span data-ttu-id="e57ef-215">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="e57ef-215">Axs Local Archive</span></span>
    
- <span data-ttu-id="e57ef-216">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="e57ef-216">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="e57ef-217">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="e57ef-217">Axs Signed</span></span>
    
- <span data-ttu-id="e57ef-218">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e57ef-218">Bloomberg</span></span>
    
- <span data-ttu-id="e57ef-219">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="e57ef-219">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="e57ef-220">Smarsh</span><span class="sxs-lookup"><span data-stu-id="e57ef-220">Smarsh</span></span>

<span data-ttu-id="e57ef-221">[Smarsh](https://www.smarsh.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-221">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e57ef-222">OBIETTIVO</span><span class="sxs-lookup"><span data-stu-id="e57ef-222">AIM</span></span>
    
- <span data-ttu-id="e57ef-223">American Idol</span><span class="sxs-lookup"><span data-stu-id="e57ef-223">American Idol</span></span>
    
- <span data-ttu-id="e57ef-224">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="e57ef-224">Apple Juice</span></span>
    
- <span data-ttu-id="e57ef-225">AOL con client Pivot</span><span class="sxs-lookup"><span data-stu-id="e57ef-225">AOL with Pivot client</span></span>
    
- <span data-ttu-id="e57ef-226">Ares</span><span class="sxs-lookup"><span data-stu-id="e57ef-226">Ares</span></span>
    
- <span data-ttu-id="e57ef-227">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-227">Bazaar Voice</span></span>
    
- <span data-ttu-id="e57ef-228">Bear Share</span><span class="sxs-lookup"><span data-stu-id="e57ef-228">Bear Share</span></span>
    
- <span data-ttu-id="e57ef-229">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="e57ef-229">Bit Torrent</span></span>
    
- <span data-ttu-id="e57ef-230">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e57ef-230">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e57ef-231">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e57ef-231">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e57ef-232">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e57ef-232">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e57ef-233">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="e57ef-233">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="e57ef-234">Posta Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e57ef-234">Bloomberg Mail</span></span>
    
- <span data-ttu-id="e57ef-235">CellTrust</span><span class="sxs-lookup"><span data-stu-id="e57ef-235">CellTrust</span></span>
    
- <span data-ttu-id="e57ef-236">Chat Import</span><span class="sxs-lookup"><span data-stu-id="e57ef-236">Chat Import</span></span>
    
- <span data-ttu-id="e57ef-237">Chat Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="e57ef-237">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="e57ef-238">Chiacchiere</span><span class="sxs-lookup"><span data-stu-id="e57ef-238">Chatter</span></span>
    
- <span data-ttu-id="e57ef-239">Server di presenza di messaggistica istantanea Cisco &amp; (v 9.0.1, v 9.1, v 9.1.1 su1, V10, v 10.5.1 su1)</span><span class="sxs-lookup"><span data-stu-id="e57ef-239">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="e57ef-240">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="e57ef-240">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="e57ef-241">Importazione collaborazione</span><span class="sxs-lookup"><span data-stu-id="e57ef-241">Collaboration Import</span></span>
    
- <span data-ttu-id="e57ef-242">Registrazione di collaborazione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="e57ef-242">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="e57ef-243">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="e57ef-243">Direct Connect</span></span>
    
- <span data-ttu-id="e57ef-244">Facebook</span><span class="sxs-lookup"><span data-stu-id="e57ef-244">Facebook</span></span>
    
- <span data-ttu-id="e57ef-245">Factt</span><span class="sxs-lookup"><span data-stu-id="e57ef-245">FactSet</span></span>
    
- <span data-ttu-id="e57ef-246">FastTrack</span><span class="sxs-lookup"><span data-stu-id="e57ef-246">FastTrack</span></span>
    
- <span data-ttu-id="e57ef-247">Gnutella</span><span class="sxs-lookup"><span data-stu-id="e57ef-247">Gnutella</span></span>
    
- <span data-ttu-id="e57ef-248">Google +</span><span class="sxs-lookup"><span data-stu-id="e57ef-248">Google+</span></span>
    
- <span data-ttu-id="e57ef-249">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="e57ef-249">GoToMyPC</span></span>
    
- <span data-ttu-id="e57ef-250">Hopster</span><span class="sxs-lookup"><span data-stu-id="e57ef-250">Hopster</span></span>
    
- <span data-ttu-id="e57ef-251">HubConnex</span><span class="sxs-lookup"><span data-stu-id="e57ef-251">HubConnex</span></span>
    
- <span data-ttu-id="e57ef-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="e57ef-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="e57ef-253">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="e57ef-253">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="e57ef-254">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="e57ef-254">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="e57ef-255">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="e57ef-255">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="e57ef-256">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="e57ef-256">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="e57ef-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="e57ef-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="e57ef-258">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="e57ef-258">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="e57ef-259">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="e57ef-259">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="e57ef-260">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="e57ef-260">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="e57ef-261">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="e57ef-261">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="e57ef-262">IM Import</span><span class="sxs-lookup"><span data-stu-id="e57ef-262">IM Import</span></span>
    
- <span data-ttu-id="e57ef-263">IM Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="e57ef-263">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="e57ef-264">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="e57ef-264">Indii Messenger</span></span>
    
- <span data-ttu-id="e57ef-265">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="e57ef-265">Instant Bloomberg</span></span>
    
- <span data-ttu-id="e57ef-266">IRC</span><span class="sxs-lookup"><span data-stu-id="e57ef-266">IRC</span></span>
    
- <span data-ttu-id="e57ef-267">Jive</span><span class="sxs-lookup"><span data-stu-id="e57ef-267">Jive</span></span>
    
- <span data-ttu-id="e57ef-268">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="e57ef-268">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="e57ef-269">Jive Import</span><span class="sxs-lookup"><span data-stu-id="e57ef-269">Jive Import</span></span>
    
- <span data-ttu-id="e57ef-270">JXTA</span><span class="sxs-lookup"><span data-stu-id="e57ef-270">JXTA</span></span>
    
- <span data-ttu-id="e57ef-271">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e57ef-271">LinkedIn</span></span>
    
- <span data-ttu-id="e57ef-272">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="e57ef-272">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="e57ef-273">MFTP</span><span class="sxs-lookup"><span data-stu-id="e57ef-273">MFTP</span></span>
    
- <span data-ttu-id="e57ef-274">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-274">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="e57ef-275">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="e57ef-275">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="e57ef-276">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e57ef-276">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="e57ef-277">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="e57ef-277">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="e57ef-278">MindAlign</span><span class="sxs-lookup"><span data-stu-id="e57ef-278">MindAlign</span></span>
    
- <span data-ttu-id="e57ef-279">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="e57ef-279">Mobile Guard</span></span>
    
- <span data-ttu-id="e57ef-280">MSN</span><span class="sxs-lookup"><span data-stu-id="e57ef-280">MSN</span></span>
    
- <span data-ttu-id="e57ef-281">My Space</span><span class="sxs-lookup"><span data-stu-id="e57ef-281">My Space</span></span>
    
- <span data-ttu-id="e57ef-282">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="e57ef-282">NEONetwork</span></span>
    
- <span data-ttu-id="e57ef-283">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="e57ef-283">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="e57ef-284">Messaggistica istantanea condivisa di Office 365</span><span class="sxs-lookup"><span data-stu-id="e57ef-284">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="e57ef-285">Pinterest</span><span class="sxs-lookup"><span data-stu-id="e57ef-285">Pinterest</span></span>
    
- <span data-ttu-id="e57ef-286">Pivot</span><span class="sxs-lookup"><span data-stu-id="e57ef-286">Pivot</span></span>
    
- <span data-ttu-id="e57ef-287">QQ</span><span class="sxs-lookup"><span data-stu-id="e57ef-287">QQ</span></span>
    
- <span data-ttu-id="e57ef-288">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="e57ef-288">Skype for Business 2015</span></span>
    
- <span data-ttu-id="e57ef-289">SoftEther</span><span class="sxs-lookup"><span data-stu-id="e57ef-289">SoftEther</span></span>
    
- <span data-ttu-id="e57ef-290">Sinfonia</span><span class="sxs-lookup"><span data-stu-id="e57ef-290">Symphony</span></span>
    
- <span data-ttu-id="e57ef-291">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="e57ef-291">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="e57ef-292">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="e57ef-292">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="e57ef-293">Tor</span><span class="sxs-lookup"><span data-stu-id="e57ef-293">Tor</span></span>
    
- <span data-ttu-id="e57ef-294">TTT</span><span class="sxs-lookup"><span data-stu-id="e57ef-294">TTT</span></span>
    
- <span data-ttu-id="e57ef-295">Twitter</span><span class="sxs-lookup"><span data-stu-id="e57ef-295">Twitter</span></span>
    
- <span data-ttu-id="e57ef-296">WinMX</span><span class="sxs-lookup"><span data-stu-id="e57ef-296">WinMX</span></span>
    
- <span data-ttu-id="e57ef-297">Winny</span><span class="sxs-lookup"><span data-stu-id="e57ef-297">Winny</span></span>
    
- <span data-ttu-id="e57ef-298">Yahoo</span><span class="sxs-lookup"><span data-stu-id="e57ef-298">Yahoo</span></span>
    
- <span data-ttu-id="e57ef-299">Yammer</span><span class="sxs-lookup"><span data-stu-id="e57ef-299">Yammer</span></span>
    
- <span data-ttu-id="e57ef-300">YouTube</span><span class="sxs-lookup"><span data-stu-id="e57ef-300">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="e57ef-301">Verba</span><span class="sxs-lookup"><span data-stu-id="e57ef-301">Verba</span></span>

<span data-ttu-id="e57ef-302">[Verba](https://www.verba.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-302">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="e57ef-303">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="e57ef-303">Avaya Aura Video</span></span>
    
- <span data-ttu-id="e57ef-304">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-304">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="e57ef-305">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="e57ef-305">Avtec Radio</span></span>
    
- <span data-ttu-id="e57ef-306">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="e57ef-306">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="e57ef-307">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="e57ef-307">BroadSoft Video</span></span>
    
- <span data-ttu-id="e57ef-308">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-308">BroadSoft Voice</span></span>
    
- <span data-ttu-id="e57ef-309">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-309">Centile Voice</span></span>
    
- <span data-ttu-id="e57ef-310">Messaggistica immediata Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="e57ef-310">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="e57ef-311">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="e57ef-311">Cisco UC Video</span></span>
    
- <span data-ttu-id="e57ef-312">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-312">Cisco UC Voice</span></span>
    
- <span data-ttu-id="e57ef-313">Video su Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="e57ef-313">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="e57ef-314">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-314">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="e57ef-315">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="e57ef-315">ESChat Radio</span></span>
    
- <span data-ttu-id="e57ef-316">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="e57ef-316">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="e57ef-317">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-317">IP Trade Voice</span></span>
    
- <span data-ttu-id="e57ef-318">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="e57ef-318">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="e57ef-319">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="e57ef-319">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="e57ef-320">Mitel MiContact Center per Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="e57ef-320">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="e57ef-321">Oracle / Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="e57ef-321">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="e57ef-322">Oracle / Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-322">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="e57ef-323">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-323">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="e57ef-324">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="e57ef-324">SIPREC Video</span></span>
    
-  <span data-ttu-id="e57ef-325">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-325">SIPREC Voice</span></span> 
    
- <span data-ttu-id="e57ef-326">Messaggistica immediata Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="e57ef-326">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="e57ef-327">Video Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="e57ef-327">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="e57ef-328">Chiamate Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="e57ef-328">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="e57ef-329">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-329">Speakerbus Voice</span></span>
    
- <span data-ttu-id="e57ef-330">Video SIP/H.323 standard</span><span class="sxs-lookup"><span data-stu-id="e57ef-330">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="e57ef-331">Chiamate SIP/H.323 standard</span><span class="sxs-lookup"><span data-stu-id="e57ef-331">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="e57ef-332">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="e57ef-332">Truphone Voice</span></span>
    
- <span data-ttu-id="e57ef-333">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="e57ef-333">TwistedPair Radio</span></span>
    
- <span data-ttu-id="e57ef-334">Schermata di Computer Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="e57ef-334">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="e57ef-335">Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="e57ef-335">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="e57ef-336">Di seguito sono riportati i passaggi per la creazione e la configurazione di una cassetta postale di dati di terze parti per l'importazione di dati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-336">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="e57ef-337">Come spiegato in precedenza, gli elementi vengono importati nella cassetta postale se il connettore partner non è in grado di mappare l'ID utente dell'elemento a un account utente.</span><span class="sxs-lookup"><span data-stu-id="e57ef-337">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an user account.</span></span>
  
 <span data-ttu-id="e57ef-338">**Completare queste attività nell'interfaccia di amministrazione di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="e57ef-338">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="e57ef-339">Creare un account utente e assegnargli una licenza di Exchange Online piano 2; vedere [aggiungere utenti a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="e57ef-339">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="e57ef-340">È necessaria una licenza di piano 2 per attivare il blocco per controversia legale o abilitare una cassetta postale di archiviazione con una quota illimitata.</span><span class="sxs-lookup"><span data-stu-id="e57ef-340">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="e57ef-341">Aggiungere l'account utente per la cassetta postale dei dati di terze parti al ruolo **amministratore di Exchange** in Office 365; Per ulteriori informazioni, vedere [assegnare ruoli di amministratore in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="e57ef-341">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e57ef-342">Annotare le credenziali per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="e57ef-342">Write down the credentials for this user account.</span></span> <span data-ttu-id="e57ef-343">È necessario fornirle al partner, come descritto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e57ef-343">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="e57ef-344">**Completare queste attività nell'interfaccia di amministrazione di Exchange**</span><span class="sxs-lookup"><span data-stu-id="e57ef-344">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="e57ef-345">Nascondere la cassetta postale dei dati di terze parti nella rubrica e negli altri elenchi di indirizzi dell'organizzazione. vedere [gestire le cassette postali degli utenti](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="e57ef-345">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="e57ef-346">In alternativa, è possibile eseguire il comando di PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="e57ef-346">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="e57ef-347">Assegnare l'autorizzazione **FullAccess** alla cassetta postale dei dati di terze parti in modo che gli amministratori o i responsabili della conformità possano aprire la cassetta postale dei dati di terze parti nel client desktop di Outlook. vedere [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="e57ef-347">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="e57ef-348">Abilitare le seguenti funzionalità correlate alla conformità per la cassetta postale dei dati di terze parti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-348">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="e57ef-349">Abilitare la cassetta postale di archiviazione; vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="e57ef-349">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="e57ef-350">In questo modo è possibile liberare spazio di archiviazione nella cassetta postale principale impostando un criterio di archiviazione che consente di spostare gli elementi di dati di terze parti nella cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e57ef-350">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="e57ef-351">In questo modo si dispone di un'archiviazione illimitata per i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-351">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="e57ef-352">Abilitare il blocco per controversia legale nella cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-352">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="e57ef-353">È anche possibile applicare un criterio di conservazione Microsoft 365 nel centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="e57ef-353">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="e57ef-354">Se la cassetta postale viene mantenuta in attesa, gli elementi di terze parti vengono conservati (indefinitamente o per una durata specificata) e impediscono che vengano eliminati dalla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e57ef-354">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="e57ef-355">Vedere uno dei seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-355">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="e57ef-356">Applicare un blocco per controversia legale a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="e57ef-356">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="e57ef-357">Informazioni sui criteri di conservazione e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="e57ef-357">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="e57ef-358">Abilitare la registrazione di controllo delle cassette postali per l'accesso proprietario, delegato e amministratore alla cassetta postale dei dati di terze parti; vedere [abilitare il controllo delle cassette postali](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="e57ef-358">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="e57ef-359">In questo modo è possibile controllare tutte le attività eseguite da qualsiasi utente che abbia accesso alla cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-359">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="e57ef-360">Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e57ef-360">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="e57ef-361">Il passaggio successivo consiste nel configurare cassette postali degli utenti per supportare i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-361">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="e57ef-362">Completare queste attività utilizzando l'interfaccia di amministrazione di Exchange o utilizzando i cmdlet di Windows PowerShell corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-362">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="e57ef-363">Abilitare la cassetta postale di archiviazione per ogni utente; vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="e57ef-363">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="e57ef-364">Inserire le cassette postali degli utenti sul blocco per controversia legale o applicare un criterio di conservazione Microsoft 365; vedere uno dei seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-364">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="e57ef-365">Applicare un blocco per controversia legale a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="e57ef-365">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="e57ef-366">Informazioni sui criteri di conservazione e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="e57ef-366">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="e57ef-367">Come precedentemente illustrato, quando si abilita un blocco delle cassette postali, è possibile impostare una durata per definire quanto tempo devono essere conservati gli elementi dell'origine dati di terze parti oppure è possibile scegliere di conservare gli elementi per un periodo di tempo indeterminato.</span><span class="sxs-lookup"><span data-stu-id="e57ef-367">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="e57ef-368">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="e57ef-368">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="e57ef-369">Il passaggio finale consiste nel fornire al partner le seguenti informazioni in modo che possano configurare il connettore per la connessione all'organizzazione per l'importazione dei dati nelle cassette postali degli utenti e nella cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-369">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="e57ef-370">Endpoint utilizzato per la connessione al servizio di Azure in Office 365:</span><span class="sxs-lookup"><span data-stu-id="e57ef-370">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="e57ef-371">Credenziali di accesso (ID utente e password di Microsoft 365) della cassetta postale di dati di terze parti creata al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="e57ef-371">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="e57ef-372">Queste credenziali sono necessarie affinché il connettore partner possa accedere e importare gli elementi nelle cassette postali degli utenti e nella cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-372">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="e57ef-373">Passaggio 5: registrare il connettore di dati di terze parti in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e57ef-373">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="e57ef-374">A partire da settembre 30, 2018, il servizio di Azure in Office 365 inizierà a utilizzare l'autenticazione moderna in Exchange Online per autenticare i connettori di dati di terze parti che tentano di connettersi alla propria organizzazione per importare i dati.</span><span class="sxs-lookup"><span data-stu-id="e57ef-374">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="e57ef-375">La causa di questa modifica consiste nel fatto che l'autenticazione moderna fornisce una maggiore sicurezza rispetto al metodo corrente, basato su un elenco Consenti per i connettori di terze parti che utilizzano l'endpoint descritto in precedenza per la connessione al servizio Azure.</span><span class="sxs-lookup"><span data-stu-id="e57ef-375">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="e57ef-376">Per abilitare un connettore di dati di terze parti per la connessione a Office 365 utilizzando il nuovo metodo di autenticazione moderno, un amministratore dell'organizzazione deve acconsentire a registrare il connettore come applicazione di servizio attendibile in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e57ef-376">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="e57ef-377">Per eseguire questa operazione, è necessario accettare una richiesta di autorizzazione per consentire al connettore di accedere ai dati dell'organizzazione in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e57ef-377">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="e57ef-378">Dopo aver accettato la richiesta, il connettore di dati di terze parti viene aggiunto come applicazione Enterprise ad Azure Active Directory e rappresentato come entità di servizio.</span><span class="sxs-lookup"><span data-stu-id="e57ef-378">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="e57ef-379">Per ulteriori informazioni sul processo di consenso, vedere [tenant admin consenso](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="e57ef-379">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="e57ef-380">Di seguito sono riportati i passaggi per accedere e accettare la richiesta di registrazione del connettore:</span><span class="sxs-lookup"><span data-stu-id="e57ef-380">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="e57ef-381">Accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e57ef-381">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="e57ef-382">Verrà visualizzata la finestra di dialogo seguente.</span><span class="sxs-lookup"><span data-stu-id="e57ef-382">The following dialog box is displayed.</span></span> <span data-ttu-id="e57ef-383">È possibile espandere le carriere per esaminare le autorizzazioni che verranno assegnate al connettore.</span><span class="sxs-lookup"><span data-stu-id="e57ef-383">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Viene visualizzata la finestra di dialogo delle richieste di autorizzazione](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="e57ef-385">Fare clic su **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="e57ef-385">Click **Accept**.</span></span>

<span data-ttu-id="e57ef-386">Dopo aver accettato la richiesta, viene visualizzato il [portale di Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="e57ef-386">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="e57ef-387">Per visualizzare l'elenco delle applicazioni per l'organizzazione, fare clic su applicazioni di **Azure Active Directory**  >  **Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="e57ef-387">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="e57ef-388">Il connettore di dati di terze parti di Office 365 è elencato nel Blade **applicazioni Enterprise** .</span><span class="sxs-lookup"><span data-stu-id="e57ef-388">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e57ef-389">Dopo il 30 settembre 2018, i dati di terze parti non verranno più importati nelle cassette postali dell'organizzazione se non si registra un connettore di dati di terze parti in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e57ef-389">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="e57ef-390">Nota i connettori di dati di terze parti esistenti (quelli creati prima del 30 settembre 2018) devono essere registrati anche in Azure Active Directory attenendosi alla procedura descritta nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="e57ef-390">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="e57ef-391">Revoca del consenso per un connettore di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="e57ef-391">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="e57ef-392">Dopo che l'organizzazione ha acconsentito alla richiesta di autorizzazione per la registrazione di un connettore di dati di terze parti in Azure Active Directory, l'organizzazione può revocare il consenso in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="e57ef-392">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="e57ef-393">Tuttavia, la revoca del consenso per un connettore significa che i dati provenienti dall'origine dati di terze parti non verranno più importati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-393">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="e57ef-394">Per revocare il consenso per un connettore di dati di terze parti, è possibile eliminare l'applicazione (eliminando l'entità di servizio corrispondente) da Azure Active Directory utilizzando il Blade **applicazioni Enterprise** nel portale di Azure o utilizzando il [Remove-msolserviceprincipal viene](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e57ef-394">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="e57ef-395">È inoltre possibile utilizzare il cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e57ef-395">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="e57ef-396">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="e57ef-396">More information</span></span>

- <span data-ttu-id="e57ef-397">Come illustrato in precedenza, gli elementi provenienti da origini dati di terze parti vengono importati nelle cassette postali di Exchange come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e57ef-397">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="e57ef-398">Il connettore partner importa l'elemento utilizzando uno schema richiesto dall'API di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-398">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="e57ef-399">Nella tabella seguente vengono descritte le proprietà del messaggio di un elemento di un'origine dati di terze parti dopo che è stato importato in una cassetta postale di Exchange come messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e57ef-399">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="e57ef-400">Nella tabella viene indicato anche se la proprietà del messaggio è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="e57ef-400">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="e57ef-401">È necessario popolare le proprietà obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="e57ef-401">Mandatory properties must be populated.</span></span> <span data-ttu-id="e57ef-402">Se un elemento è mancante di una proprietà obbligatoria, non verrà importato in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-402">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="e57ef-403">Il processo di importazione restituisce un messaggio di errore che spiega il motivo per cui un elemento non è stato importato e la proprietà mancante.</span><span class="sxs-lookup"><span data-stu-id="e57ef-403">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="e57ef-404">**Proprietà del messaggio**</span><span class="sxs-lookup"><span data-stu-id="e57ef-404">**Message property**</span></span>|<span data-ttu-id="e57ef-405">**Obbligatorio?**</span><span class="sxs-lookup"><span data-stu-id="e57ef-405">**Mandatory?**</span></span>|<span data-ttu-id="e57ef-406">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e57ef-406">**Description**</span></span>|<span data-ttu-id="e57ef-407">**Valore di esempio**</span><span class="sxs-lookup"><span data-stu-id="e57ef-407">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e57ef-408">**Da**</span><span class="sxs-lookup"><span data-stu-id="e57ef-408">**FROM**</span></span> <br/> |<span data-ttu-id="e57ef-409">Sì</span><span class="sxs-lookup"><span data-stu-id="e57ef-409">Yes</span></span>  <br/> |<span data-ttu-id="e57ef-410">L'utente che ha originariamente creato o inviato l'elemento nell'origine dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-410">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="e57ef-411">Il connettore partner tenta di mappare l'ID utente dall'elemento di origine (ad esempio un handle Twitter) a un account utente per tutti i partecipanti (utenti nei campi da e a).</span><span class="sxs-lookup"><span data-stu-id="e57ef-411">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="e57ef-412">Verrà importata una copia del messaggio nella cassetta postale di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="e57ef-412">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="e57ef-413">Se non è possibile eseguire il mapping di nessuno dei partecipanti dall'elemento a un account utente, l'elemento verrà importato nella cassetta postale di archiviazione di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e57ef-413">If none of the participants from the item can be mapped to an user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="e57ef-414">Il partecipante identificato come mittente dell'elemento deve disporre di una cassetta postale attiva nell'organizzazione a cui l'elemento viene importato.</span><span class="sxs-lookup"><span data-stu-id="e57ef-414">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="e57ef-415">In caso contrario, viene restituito l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="e57ef-415">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="e57ef-416">**A**</span><span class="sxs-lookup"><span data-stu-id="e57ef-416">**TO**</span></span> <br/> |<span data-ttu-id="e57ef-417">Sì</span><span class="sxs-lookup"><span data-stu-id="e57ef-417">Yes</span></span>  <br/> |<span data-ttu-id="e57ef-418">L'utente che ha ricevuto un elemento, se applicabile per un elemento nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e57ef-418">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="e57ef-419">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="e57ef-419">**SUBJECT**</span></span> <br/> |<span data-ttu-id="e57ef-420">No</span><span class="sxs-lookup"><span data-stu-id="e57ef-420">No</span></span>  <br/> |<span data-ttu-id="e57ef-421">L'oggetto dell'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="e57ef-421">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="e57ef-422">**Data**</span><span class="sxs-lookup"><span data-stu-id="e57ef-422">**DATE**</span></span> <br/> |<span data-ttu-id="e57ef-423">Sì</span><span class="sxs-lookup"><span data-stu-id="e57ef-423">Yes</span></span>  <br/> |<span data-ttu-id="e57ef-424">La data in cui l'elemento è stato originariamente creato o pubblicato nell'origine dati del cliente.</span><span class="sxs-lookup"><span data-stu-id="e57ef-424">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="e57ef-425">Ad esempio, la data in cui un messaggio Twitter è stato tweeted.</span><span class="sxs-lookup"><span data-stu-id="e57ef-425">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="e57ef-426">**CORPO**</span><span class="sxs-lookup"><span data-stu-id="e57ef-426">**BODY**</span></span> <br/> |<span data-ttu-id="e57ef-427">No</span><span class="sxs-lookup"><span data-stu-id="e57ef-427">No</span></span>  <br/> |<span data-ttu-id="e57ef-428">Il contenuto del messaggio o del post.</span><span class="sxs-lookup"><span data-stu-id="e57ef-428">The contents of the message or post.</span></span> <span data-ttu-id="e57ef-429">Per alcune origini dati, il contenuto di questa proprietà può corrispondere al contenuto della proprietà **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="e57ef-429">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="e57ef-430">Durante il processo di importazione, il connettore del partner tenta di mantenere la fedeltà completa dall'origine di contenuto il più possibile.</span><span class="sxs-lookup"><span data-stu-id="e57ef-430">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="e57ef-431">Se possibile, i file, gli elementi grafici o altri contenuti del corpo dell'elemento di origine sono inclusi in questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="e57ef-431">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="e57ef-432">In caso contrario, il contenuto dell'elemento di origine è incluso nella proprietà **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="e57ef-432">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="e57ef-433">I contenuti di questa proprietà dipendono dal connettore del partner e dalla funzionalità della piattaforma di origine.</span><span class="sxs-lookup"><span data-stu-id="e57ef-433">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="e57ef-434">**ALLEGATO**</span><span class="sxs-lookup"><span data-stu-id="e57ef-434">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="e57ef-435">No</span><span class="sxs-lookup"><span data-stu-id="e57ef-435">No</span></span>  <br/> |<span data-ttu-id="e57ef-436">Se un elemento nell'origine dati, ad esempio un tweet in Twitter o una conversazione di messaggistica istantanea, ha un file allegato o include immagini, la connessione del partner tenterà innanzitutto di includere gli allegati nella proprietà **Body** .</span><span class="sxs-lookup"><span data-stu-id="e57ef-436">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="e57ef-437">Se non è possibile, allora viene aggiunto alla proprietà \* \* ATTACHMENT \* \*.</span><span class="sxs-lookup"><span data-stu-id="e57ef-437">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="e57ef-438">Altri esempi di allegati sono i Like su Facebook, i metadati dell'origine del contenuto e le risposte a un messaggio o a un post.</span><span class="sxs-lookup"><span data-stu-id="e57ef-438">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="e57ef-439">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="e57ef-439">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="e57ef-440">Sì</span><span class="sxs-lookup"><span data-stu-id="e57ef-440">Yes</span></span>  <br/> | <span data-ttu-id="e57ef-441">Si tratta di una proprietà multivalore, che viene creata e compilata dal connettore partner.</span><span class="sxs-lookup"><span data-stu-id="e57ef-441">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="e57ef-442">Il formato di questa proprietà è `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="e57ef-442">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="e57ef-443">Questa proprietà deve iniziare con `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="e57ef-443">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="e57ef-444">Questo formato è simile a quello della `IPM.NOTE.X` classe Message. Questa proprietà include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e57ef-444">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="e57ef-445">`Source`: Indica l'origine dati di terze parti; ad esempio, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="e57ef-445">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="e57ef-446">`Event`: Indica il tipo di attività eseguita nell'origine dati di terze parti che ha prodotto gli elementi; ad esempio, un tweet in Twitter o un post in Facebook.</span><span class="sxs-lookup"><span data-stu-id="e57ef-446">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="e57ef-447">Gli eventi sono specifici per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e57ef-447">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="e57ef-448">Uno scopo di questa proprietà risiede nel filtrare gli elementi specifici in base all'origine dati in cui un elemento ha avuto origine o in base al tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="e57ef-448">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="e57ef-449">In una ricerca eDiscovery, ad esempio, è possibile creare una query di ricerca per trovare tutti i tweet pubblicati da un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="e57ef-449">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="e57ef-450">Quando gli elementi vengono importati correttamente nelle cassette postali di Office 365, viene restituito un identificatore univoco al chiamante come parte della risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="e57ef-450">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="e57ef-451">Questo identificatore, denominato `x-IngestionCorrelationID` , può essere utilizzato per la risoluzione dei problemi successivi da parte di partner per il monitoraggio end-to-end degli elementi.</span><span class="sxs-lookup"><span data-stu-id="e57ef-451">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="e57ef-452">Si consiglia di raccogliere queste informazioni e registrarle nel modo più appropriato.</span><span class="sxs-lookup"><span data-stu-id="e57ef-452">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="e57ef-453">Di seguito è riportato un esempio di una risposta HTTP che mostra l'identificatore:</span><span class="sxs-lookup"><span data-stu-id="e57ef-453">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="e57ef-454">È possibile utilizzare lo strumento di ricerca contenuto nel centro sicurezza e conformità per cercare gli elementi importati nelle cassette postali da un'origine dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-454">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="e57ef-455">Per eseguire la ricerca in modo specifico per questi elementi importati, è possibile utilizzare le seguenti coppie proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="e57ef-455">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="e57ef-456">**`kind:externaldata`**: Utilizzare questa coppia proprietà-valore per eseguire la ricerca in tutti i tipi di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-456">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="e57ef-457">Ad esempio, per cercare gli elementi importati da un'origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query di parole chiave `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="e57ef-457">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="e57ef-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Utilizzare questa coppia proprietà-valore per cercare solo un tipo di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e57ef-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="e57ef-459">Ad esempio, per cercare solo i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query di parole chiave `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="e57ef-459">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="e57ef-460">Per un elenco completo dei valori da utilizzare per i tipi di dati di terze parti per la `itemclass` proprietà, vedere [utilizzare Ricerca contenuto per cercare i dati di terze parti che sono stati importati in Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span><span class="sxs-lookup"><span data-stu-id="e57ef-460">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="e57ef-461">Per ulteriori informazioni sull'utilizzo di Ricerca contenuto e sulla creazione di query di ricerca con parole chiave, vedere:</span><span class="sxs-lookup"><span data-stu-id="e57ef-461">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="e57ef-462">Ricerca contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="e57ef-462">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="e57ef-463">Query con parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="e57ef-463">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
