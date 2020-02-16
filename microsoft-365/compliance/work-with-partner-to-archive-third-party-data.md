---
title: Collaborare con un partner per archiviare i dati di terze parti in Office 365
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
ms.collection: M365-security-compliance
description: L'organizzazione può collaborare con un partner Microsoft per configurare un connettore personalizzato per l'importazione di dati di terze parti da origini dati quali Salesforce Chatter, Yahoo Messenger o Yammer. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Office 365 per poter utilizzare le funzionalità di conformità di Office 365, ad esempio i criteri di conservazione legale, ricerca contenuto e ritenzione per gestire la governance dei dati di terze parti dell'organizzazione.
ms.openlocfilehash: 6104381b842b9a4d76de7278c0b7280ec2f11222
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085017"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a><span data-ttu-id="6fcc1-104">Collaborare con un partner per archiviare i dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="6fcc1-104">Work with a partner to archive third-party data in Office 365</span></span>

<span data-ttu-id="6fcc1-105">È possibile collaborare con un partner Microsoft per importare e archiviare i dati da un'origine dati di terze parti a Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-105">You can work with a Microsoft Partner to import and archive data from a third-party data source to Office 365.</span></span> <span data-ttu-id="6fcc1-106">Un partner può fornire un connettore personalizzato configurato per estrarre elementi dall'origine dati di terze parti (su base regolare) e quindi importare tali elementi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-106">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items to Office 365.</span></span> <span data-ttu-id="6fcc1-107">Il connettore partner converte il contenuto di un elemento dall'origine dati in un formato di messaggio di posta elettronica e quindi archivia gli elementi nelle cassette postali in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-107">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes in Office 365.</span></span> <span data-ttu-id="6fcc1-108">Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo e i criteri di conservazione di Office 365 ai dati.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-108">After third-party data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to this data.</span></span>
  
<span data-ttu-id="6fcc1-109">Di seguito è riportata una panoramica del processo e i passaggi necessari per collaborare con un partner Microsoft per importare i dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data to Office 365.</span></span>

[<span data-ttu-id="6fcc1-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="6fcc1-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="6fcc1-111">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="6fcc1-111">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="6fcc1-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="6fcc1-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="6fcc1-113">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="6fcc1-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="6fcc1-114">Passaggio 5: registrare il connettore di dati di terze parti in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6fcc1-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="6fcc1-115">Funzionamento del processo di importazione dei dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="6fcc1-115">How the third-party data import process works</span></span>

<span data-ttu-id="6fcc1-116">Nella figura e nella descrizione seguenti viene illustrato il funzionamento del processo di importazione di dati di terze parti quando si lavora con un partner.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Funzionamento del processo di importazione dei dati di terze parti](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="6fcc1-118">Il cliente lavora con il proprio partner preferito per configurare un connettore che estrae gli elementi dall'origine dati di terze parti e quindi importa tali elementi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="6fcc1-119">Il connettore partner si connette a origini dati di terze parti tramite un'API di terze parti (su base pianificata o configurata) ed estrae gli elementi dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="6fcc1-120">Il connettore partner converte il contenuto di un elemento in un formato di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="6fcc1-121">Vedere la sezione [ulteriori informazioni](#more-information) per una descrizione dello schema del formato dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="6fcc1-122">Il connettore partner si connette al servizio di Azure in Office 365 utilizzando il servizio Web Exchange (EWS) tramite un punto finale noto.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-122">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="6fcc1-p104">Gli elementi vengono importati nella cassetta postale di un utente specifico oppure in una cassetta postale generale di dati di terze parti. Il fatto che un elemento sia importato nella cassetta postale di un utente specifico o nella cassetta postale di dati di terze parti dipende dai seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-p104">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="6fcc1-125">a.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-125">a.</span></span> <span data-ttu-id="6fcc1-126">**Elementi che dispongono di un ID utente corrispondente a un account utente di Office 365:** Se il connettore partner è in grado di eseguire il mapping dell'ID utente dell'elemento nell'origine dati di terze parti a un ID utente specifico in Office 365, l'elemento viene copiato nella cartella **Purges** nella cartella elementi ripristinabili dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-126">**Items that have a user ID that corresponds to an Office 365 user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="6fcc1-127">Gli utenti non possono accedere agli elementi nella cartella Ripuliture.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-127">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="6fcc1-128">Tuttavia, è possibile utilizzare gli strumenti di Office 365 eDiscovery per cercare gli elementi nella cartella Purges.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-128">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="6fcc1-129">b.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-129">b.</span></span> <span data-ttu-id="6fcc1-130">**Elementi che non dispongono di un ID utente corrispondente a un account utente di Office 365:** Se il connettore partner non è in grado di eseguire il mapping dell'ID utente di un elemento a un ID utente specifico in Office 365, l'elemento viene copiato nella cartella **posta in arrivo** della cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-130">**Items that don't have a user ID that corresponds to an Office 365 user account:** If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="6fcc1-131">L'importazione di elementi nella posta in arrivo consente a un utente dell'organizzazione di accedere alla cassetta postale di terze parti per visualizzare e gestire questi elementi e vedere se è necessario prevedere modifiche nella configurazione del connettore partner.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-131">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="6fcc1-132">Passaggio 1: trovare un partner di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="6fcc1-132">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="6fcc1-133">Un componente chiave per l'archiviazione dei dati di terze parti in Office 365 è l'individuazione e l'utilizzo di un partner Microsoft specializzato nell'acquisizione dei dati da un'origine dati di terze parti e nell'importarlo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-133">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="6fcc1-134">Dopo aver importato i dati, è possibile archiviarli e conservarli insieme agli altri dati di Microsoft dell'organizzazione, ad esempio la posta elettronica da Exchange e i documenti di SharePoint e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-134">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="6fcc1-135">Un partner crea un connettore che estrae i dati dalle origini dati di terze parti dell'organizzazione (ad esempio, BlackBerry, Facebook, Google +, Thomson Reuters, Twitter e YouTube) e passa tali dati a un'API di Office 365 che importa gli elementi nelle cassette postali di Exchange come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-135">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="6fcc1-136">Nelle sezioni seguenti vengono elencati i partner Microsoft e le origini dati di terze parti che supportano, che partecipano al programma per l'archiviazione dei dati di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-136">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="6fcc1-137">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="6fcc1-137">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="6fcc1-138">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="6fcc1-138">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="6fcc1-139">Globanet</span><span class="sxs-lookup"><span data-stu-id="6fcc1-139">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="6fcc1-140">OpenText</span><span class="sxs-lookup"><span data-stu-id="6fcc1-140">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="6fcc1-141">Smarsh</span><span class="sxs-lookup"><span data-stu-id="6fcc1-141">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="6fcc1-142">Verba</span><span class="sxs-lookup"><span data-stu-id="6fcc1-142">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="6fcc1-143">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="6fcc1-143">17a-4 LLC</span></span>

<span data-ttu-id="6fcc1-144">[17a-4 LLC](https://www.17a-4.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-144">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="6fcc1-145">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="6fcc1-145">BlackBerry</span></span>
    
- <span data-ttu-id="6fcc1-146">Flussi di dati di Bloomberg</span><span class="sxs-lookup"><span data-stu-id="6fcc1-146">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="6fcc1-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="6fcc1-147">Cisco Jabber</span></span>
    
- <span data-ttu-id="6fcc1-148">Factt</span><span class="sxs-lookup"><span data-stu-id="6fcc1-148">FactSet</span></span>
    
- <span data-ttu-id="6fcc1-149">HipChat</span><span class="sxs-lookup"><span data-stu-id="6fcc1-149">HipChat</span></span>
    
- <span data-ttu-id="6fcc1-150">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="6fcc1-150">InvestEdge</span></span>
    
- <span data-ttu-id="6fcc1-151">LivePerson</span><span class="sxs-lookup"><span data-stu-id="6fcc1-151">LivePerson</span></span>
    
- <span data-ttu-id="6fcc1-152">Flussi di dati MessageLabs</span><span class="sxs-lookup"><span data-stu-id="6fcc1-152">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="6fcc1-153">OpenText</span><span class="sxs-lookup"><span data-stu-id="6fcc1-153">OpenText</span></span>
    
- <span data-ttu-id="6fcc1-154">Guida "click-to-call" di Oracle/ATG</span><span class="sxs-lookup"><span data-stu-id="6fcc1-154">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="6fcc1-155">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="6fcc1-155">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="6fcc1-156">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="6fcc1-156">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="6fcc1-157">MindAlign</span><span class="sxs-lookup"><span data-stu-id="6fcc1-157">MindAlign</span></span>
    
- <span data-ttu-id="6fcc1-158">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-158">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="6fcc1-159">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-159">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="6fcc1-160">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-160">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="6fcc1-161">Database SQL</span><span class="sxs-lookup"><span data-stu-id="6fcc1-161">SQL Databases</span></span>
    
- <span data-ttu-id="6fcc1-162">Squawker</span><span class="sxs-lookup"><span data-stu-id="6fcc1-162">Squawker</span></span>
    
- <span data-ttu-id="6fcc1-163">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="6fcc1-163">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="6fcc1-164">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="6fcc1-164">ArchiveSocial</span></span>

<span data-ttu-id="6fcc1-165">[ArchiveSocial](https://www.archivesocial.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-165">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="6fcc1-166">Facebook</span><span class="sxs-lookup"><span data-stu-id="6fcc1-166">Facebook</span></span>
    
- <span data-ttu-id="6fcc1-167">Flickr</span><span class="sxs-lookup"><span data-stu-id="6fcc1-167">Flickr</span></span>
    
- <span data-ttu-id="6fcc1-168">Instagram</span><span class="sxs-lookup"><span data-stu-id="6fcc1-168">Instagram</span></span>
    
- <span data-ttu-id="6fcc1-169">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="6fcc1-169">LinkedIn</span></span>
    
- <span data-ttu-id="6fcc1-170">Pinterest</span><span class="sxs-lookup"><span data-stu-id="6fcc1-170">Pinterest</span></span>
    
- <span data-ttu-id="6fcc1-171">Twitter</span><span class="sxs-lookup"><span data-stu-id="6fcc1-171">Twitter</span></span>
    
- <span data-ttu-id="6fcc1-172">YouTube</span><span class="sxs-lookup"><span data-stu-id="6fcc1-172">YouTube</span></span>
    
- <span data-ttu-id="6fcc1-173">Officemix</span><span class="sxs-lookup"><span data-stu-id="6fcc1-173">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="6fcc1-174">Globanet</span><span class="sxs-lookup"><span data-stu-id="6fcc1-174">Globanet</span></span>

<span data-ttu-id="6fcc1-175">[Globanet](https://www.globanet.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-175">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="6fcc1-176">AOL con Pivot Client </span><span class="sxs-lookup"><span data-stu-id="6fcc1-176">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="6fcc1-177">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-177">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="6fcc1-178">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-178">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="6fcc1-179">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-179">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="6fcc1-180">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-180">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="6fcc1-181">Chat Bloomber</span><span class="sxs-lookup"><span data-stu-id="6fcc1-181">Bloomberg Chat</span></span>
    
- <span data-ttu-id="6fcc1-182">Posta Bloomberg</span><span class="sxs-lookup"><span data-stu-id="6fcc1-182">Bloomberg Mail</span></span>
    
- <span data-ttu-id="6fcc1-183">Box</span><span class="sxs-lookup"><span data-stu-id="6fcc1-183">Box</span></span>
    
- <span data-ttu-id="6fcc1-184">CipherCloud per Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="6fcc1-184">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="6fcc1-185">Server di &amp; presenza di messaggistica istantanea Cisco (V10, v 10.5.1 su1, v 11.0, v 11,5 SU2)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-185">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="6fcc1-186">Team Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="6fcc1-186">Cisco Webex Teams</span></span>

- <span data-ttu-id="6fcc1-187">ShareFile di &amp; area di lavoro Citrix</span><span class="sxs-lookup"><span data-stu-id="6fcc1-187">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="6fcc1-188">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="6fcc1-188">CrowdCompass</span></span>

- <span data-ttu-id="6fcc1-189">File di testo con valori delimitati da personalizzato</span><span class="sxs-lookup"><span data-stu-id="6fcc1-189">Custom-delimited text files</span></span>
    
- <span data-ttu-id="6fcc1-190">File XML personalizzati</span><span class="sxs-lookup"><span data-stu-id="6fcc1-190">Custom XML files</span></span>
    
- <span data-ttu-id="6fcc1-191">Facebook (pagine)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-191">Facebook (Pages)</span></span>
    
- <span data-ttu-id="6fcc1-192">Factt</span><span class="sxs-lookup"><span data-stu-id="6fcc1-192">Factset</span></span>
    
- <span data-ttu-id="6fcc1-193">FXConnect</span><span class="sxs-lookup"><span data-stu-id="6fcc1-193">FXConnect</span></span>
    
- <span data-ttu-id="6fcc1-194">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="6fcc1-194">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="6fcc1-195">Jive</span><span class="sxs-lookup"><span data-stu-id="6fcc1-195">Jive</span></span>
    
- <span data-ttu-id="6fcc1-196">XIP Macgregor</span><span class="sxs-lookup"><span data-stu-id="6fcc1-196">Macgregor XIP</span></span>

- <span data-ttu-id="6fcc1-197">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6fcc1-197">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="6fcc1-198">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="6fcc1-198">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="6fcc1-199">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6fcc1-199">Microsoft Teams</span></span>
       
- <span data-ttu-id="6fcc1-200">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="6fcc1-200">Microsoft Yammer</span></span>
    
- <span data-ttu-id="6fcc1-201">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="6fcc1-201">Mobile Guard</span></span>
    
- <span data-ttu-id="6fcc1-202">Pivot</span><span class="sxs-lookup"><span data-stu-id="6fcc1-202">Pivot</span></span>
    
- <span data-ttu-id="6fcc1-203">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="6fcc1-203">Salesforce Chatter</span></span>

- <span data-ttu-id="6fcc1-204">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6fcc1-204">Skype for Business Online</span></span>
    
- <span data-ttu-id="6fcc1-205">Skype for Business, versioni 2007 R2 - 2016 (locale)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-205">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="6fcc1-206">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="6fcc1-206">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="6fcc1-207">Sinfonia</span><span class="sxs-lookup"><span data-stu-id="6fcc1-207">Symphony</span></span>
    
- <span data-ttu-id="6fcc1-208">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="6fcc1-208">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="6fcc1-209">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="6fcc1-209">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="6fcc1-210">Thomson Reuters Dealings 3000/FX Trading</span><span class="sxs-lookup"><span data-stu-id="6fcc1-210">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="6fcc1-211">Twitter</span><span class="sxs-lookup"><span data-stu-id="6fcc1-211">Twitter</span></span>
    
- <span data-ttu-id="6fcc1-212">Chat UBS</span><span class="sxs-lookup"><span data-stu-id="6fcc1-212">UBS Chat</span></span>
    
- <span data-ttu-id="6fcc1-213">YouTube</span><span class="sxs-lookup"><span data-stu-id="6fcc1-213">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="6fcc1-214">OpenText</span><span class="sxs-lookup"><span data-stu-id="6fcc1-214">OpenText</span></span>

<span data-ttu-id="6fcc1-215">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-215">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="6fcc1-216">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="6fcc1-216">Axs Encrypted</span></span>
    
- <span data-ttu-id="6fcc1-217">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="6fcc1-217">Axs Exchange</span></span>
    
- <span data-ttu-id="6fcc1-218">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="6fcc1-218">Axs Local Archive</span></span>
    
- <span data-ttu-id="6fcc1-219">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="6fcc1-219">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="6fcc1-220">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="6fcc1-220">Axs Signed</span></span>
    
- <span data-ttu-id="6fcc1-221">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="6fcc1-221">Bloomberg</span></span>
    
- <span data-ttu-id="6fcc1-222">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="6fcc1-222">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="6fcc1-223">Smarsh</span><span class="sxs-lookup"><span data-stu-id="6fcc1-223">Smarsh</span></span>

<span data-ttu-id="6fcc1-224">[Smarsh](https://www.smarsh.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-224">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="6fcc1-225">OBIETTIVO</span><span class="sxs-lookup"><span data-stu-id="6fcc1-225">AIM</span></span>
    
- <span data-ttu-id="6fcc1-226">American Idol</span><span class="sxs-lookup"><span data-stu-id="6fcc1-226">American Idol</span></span>
    
- <span data-ttu-id="6fcc1-227">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-227">Apple Juice</span></span>
    
- <span data-ttu-id="6fcc1-228">AOL con client Pivot</span><span class="sxs-lookup"><span data-stu-id="6fcc1-228">AOL with Pivot client</span></span>
    
- <span data-ttu-id="6fcc1-229">Ares</span><span class="sxs-lookup"><span data-stu-id="6fcc1-229">Ares</span></span>
    
- <span data-ttu-id="6fcc1-230">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-230">Bazaar Voice</span></span>
    
- <span data-ttu-id="6fcc1-231">Bear Share</span><span class="sxs-lookup"><span data-stu-id="6fcc1-231">Bear Share</span></span>
    
- <span data-ttu-id="6fcc1-232">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="6fcc1-232">Bit Torrent</span></span>
    
- <span data-ttu-id="6fcc1-233">Registri chiamate BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-233">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="6fcc1-234">Messenger BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-234">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="6fcc1-235">PIN BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-235">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="6fcc1-236">SMS BlackBerry (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-236">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="6fcc1-237">Posta Bloomberg</span><span class="sxs-lookup"><span data-stu-id="6fcc1-237">Bloomberg Mail</span></span>
    
- <span data-ttu-id="6fcc1-238">CellTrust</span><span class="sxs-lookup"><span data-stu-id="6fcc1-238">CellTrust</span></span>
    
- <span data-ttu-id="6fcc1-239">Chat Import</span><span class="sxs-lookup"><span data-stu-id="6fcc1-239">Chat Import</span></span>
    
- <span data-ttu-id="6fcc1-240">Chat Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="6fcc1-240">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="6fcc1-241">Chiacchiere</span><span class="sxs-lookup"><span data-stu-id="6fcc1-241">Chatter</span></span>
    
- <span data-ttu-id="6fcc1-242">Server di &amp; presenza di messaggistica istantanea Cisco (v 9.0.1, v 9.1, v 9.1.1 su1, V10, v 10.5.1 su1)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-242">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="6fcc1-243">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-243">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="6fcc1-244">Importazione collaborazione</span><span class="sxs-lookup"><span data-stu-id="6fcc1-244">Collaboration Import</span></span>
    
- <span data-ttu-id="6fcc1-245">Registrazione di collaborazione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="6fcc1-245">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="6fcc1-246">Connessione diretta</span><span class="sxs-lookup"><span data-stu-id="6fcc1-246">Direct Connect</span></span>
    
- <span data-ttu-id="6fcc1-247">Facebook</span><span class="sxs-lookup"><span data-stu-id="6fcc1-247">Facebook</span></span>
    
- <span data-ttu-id="6fcc1-248">Factt</span><span class="sxs-lookup"><span data-stu-id="6fcc1-248">FactSet</span></span>
    
- <span data-ttu-id="6fcc1-249">FastTrack</span><span class="sxs-lookup"><span data-stu-id="6fcc1-249">FastTrack</span></span>
    
- <span data-ttu-id="6fcc1-250">Gnutella</span><span class="sxs-lookup"><span data-stu-id="6fcc1-250">Gnutella</span></span>
    
- <span data-ttu-id="6fcc1-251">Google +</span><span class="sxs-lookup"><span data-stu-id="6fcc1-251">Google+</span></span>
    
- <span data-ttu-id="6fcc1-252">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="6fcc1-252">GoToMyPC</span></span>
    
- <span data-ttu-id="6fcc1-253">Hopster</span><span class="sxs-lookup"><span data-stu-id="6fcc1-253">Hopster</span></span>
    
- <span data-ttu-id="6fcc1-254">HubConnex</span><span class="sxs-lookup"><span data-stu-id="6fcc1-254">HubConnex</span></span>
    
- <span data-ttu-id="6fcc1-255">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-255">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="6fcc1-256">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="6fcc1-256">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="6fcc1-257">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="6fcc1-257">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="6fcc1-258">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="6fcc1-258">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="6fcc1-259">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="6fcc1-259">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="6fcc1-260">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-260">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="6fcc1-261">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="6fcc1-261">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="6fcc1-262">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="6fcc1-262">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="6fcc1-263">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="6fcc1-263">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="6fcc1-264">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="6fcc1-264">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="6fcc1-265">IM Import</span><span class="sxs-lookup"><span data-stu-id="6fcc1-265">IM Import</span></span>
    
- <span data-ttu-id="6fcc1-266">IM Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="6fcc1-266">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="6fcc1-267">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="6fcc1-267">Indii Messenger</span></span>
    
- <span data-ttu-id="6fcc1-268">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="6fcc1-268">Instant Bloomberg</span></span>
    
- <span data-ttu-id="6fcc1-269">IRC</span><span class="sxs-lookup"><span data-stu-id="6fcc1-269">IRC</span></span>
    
- <span data-ttu-id="6fcc1-270">Jive</span><span class="sxs-lookup"><span data-stu-id="6fcc1-270">Jive</span></span>
    
- <span data-ttu-id="6fcc1-271">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-271">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="6fcc1-272">Jive Import</span><span class="sxs-lookup"><span data-stu-id="6fcc1-272">Jive Import</span></span>
    
- <span data-ttu-id="6fcc1-273">JXTA</span><span class="sxs-lookup"><span data-stu-id="6fcc1-273">JXTA</span></span>
    
- <span data-ttu-id="6fcc1-274">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="6fcc1-274">LinkedIn</span></span>
    
- <span data-ttu-id="6fcc1-275">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-275">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="6fcc1-276">MFTP</span><span class="sxs-lookup"><span data-stu-id="6fcc1-276">MFTP</span></span>
    
- <span data-ttu-id="6fcc1-277">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-277">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="6fcc1-278">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-278">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="6fcc1-279">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6fcc1-279">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="6fcc1-280">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-280">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="6fcc1-281">MindAlign</span><span class="sxs-lookup"><span data-stu-id="6fcc1-281">MindAlign</span></span>
    
- <span data-ttu-id="6fcc1-282">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="6fcc1-282">Mobile Guard</span></span>
    
- <span data-ttu-id="6fcc1-283">MSN</span><span class="sxs-lookup"><span data-stu-id="6fcc1-283">MSN</span></span>
    
- <span data-ttu-id="6fcc1-284">My Space</span><span class="sxs-lookup"><span data-stu-id="6fcc1-284">My Space</span></span>
    
- <span data-ttu-id="6fcc1-285">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="6fcc1-285">NEONetwork</span></span>
    
- <span data-ttu-id="6fcc1-286">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="6fcc1-286">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="6fcc1-287">Messaggistica istantanea condivisa di Office 365</span><span class="sxs-lookup"><span data-stu-id="6fcc1-287">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="6fcc1-288">Pinterest</span><span class="sxs-lookup"><span data-stu-id="6fcc1-288">Pinterest</span></span>
    
- <span data-ttu-id="6fcc1-289">Pivot</span><span class="sxs-lookup"><span data-stu-id="6fcc1-289">Pivot</span></span>
    
- <span data-ttu-id="6fcc1-290">QQ</span><span class="sxs-lookup"><span data-stu-id="6fcc1-290">QQ</span></span>
    
- <span data-ttu-id="6fcc1-291">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="6fcc1-291">Skype for Business 2015</span></span>
    
- <span data-ttu-id="6fcc1-292">SoftEther</span><span class="sxs-lookup"><span data-stu-id="6fcc1-292">SoftEther</span></span>
    
- <span data-ttu-id="6fcc1-293">Sinfonia</span><span class="sxs-lookup"><span data-stu-id="6fcc1-293">Symphony</span></span>
    
- <span data-ttu-id="6fcc1-294">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="6fcc1-294">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="6fcc1-295">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="6fcc1-295">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="6fcc1-296">Tor</span><span class="sxs-lookup"><span data-stu-id="6fcc1-296">Tor</span></span>
    
- <span data-ttu-id="6fcc1-297">TTT</span><span class="sxs-lookup"><span data-stu-id="6fcc1-297">TTT</span></span>
    
- <span data-ttu-id="6fcc1-298">Twitter</span><span class="sxs-lookup"><span data-stu-id="6fcc1-298">Twitter</span></span>
    
- <span data-ttu-id="6fcc1-299">WinMX</span><span class="sxs-lookup"><span data-stu-id="6fcc1-299">WinMX</span></span>
    
- <span data-ttu-id="6fcc1-300">Winny</span><span class="sxs-lookup"><span data-stu-id="6fcc1-300">Winny</span></span>
    
- <span data-ttu-id="6fcc1-301">Yahoo</span><span class="sxs-lookup"><span data-stu-id="6fcc1-301">Yahoo</span></span>
    
- <span data-ttu-id="6fcc1-302">Yammer</span><span class="sxs-lookup"><span data-stu-id="6fcc1-302">Yammer</span></span>
    
- <span data-ttu-id="6fcc1-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="6fcc1-303">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="6fcc1-304">Verba</span><span class="sxs-lookup"><span data-stu-id="6fcc1-304">Verba</span></span>

<span data-ttu-id="6fcc1-305">[Verba](https://www.verba.com) supporta le origini dati di terze parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-305">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="6fcc1-306">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="6fcc1-306">Avaya Aura Video</span></span>
    
- <span data-ttu-id="6fcc1-307">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-307">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="6fcc1-308">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="6fcc1-308">Avtec Radio</span></span>
    
- <span data-ttu-id="6fcc1-309">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="6fcc1-309">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="6fcc1-310">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="6fcc1-310">BroadSoft Video</span></span>
    
- <span data-ttu-id="6fcc1-311">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-311">BroadSoft Voice</span></span>
    
- <span data-ttu-id="6fcc1-312">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-312">Centile Voice</span></span>
    
- <span data-ttu-id="6fcc1-313">Messaggistica immediata Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="6fcc1-313">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="6fcc1-314">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="6fcc1-314">Cisco UC Video</span></span>
    
- <span data-ttu-id="6fcc1-315">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-315">Cisco UC Voice</span></span>
    
- <span data-ttu-id="6fcc1-316">Video su Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="6fcc1-316">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="6fcc1-317">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-317">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="6fcc1-318">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="6fcc1-318">ESChat Radio</span></span>
    
- <span data-ttu-id="6fcc1-319">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="6fcc1-319">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="6fcc1-320">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-320">IP Trade Voice</span></span>
    
- <span data-ttu-id="6fcc1-321">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="6fcc1-321">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="6fcc1-322">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-322">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="6fcc1-323">Mitel MiContact Center per Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-323">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="6fcc1-324">Oracle / Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="6fcc1-324">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="6fcc1-325">Oracle / Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-325">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="6fcc1-326">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-326">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="6fcc1-327">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="6fcc1-327">SIPREC Video</span></span>
    
-  <span data-ttu-id="6fcc1-328">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-328">SIPREC Voice</span></span> 
    
- <span data-ttu-id="6fcc1-329">Messaggistica immediata Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="6fcc1-329">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="6fcc1-330">Video Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="6fcc1-330">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="6fcc1-331">Chiamate Skype for Business / Lync</span><span class="sxs-lookup"><span data-stu-id="6fcc1-331">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="6fcc1-332">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-332">Speakerbus Voice</span></span>
    
- <span data-ttu-id="6fcc1-333">Video SIP/H.323 standard</span><span class="sxs-lookup"><span data-stu-id="6fcc1-333">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="6fcc1-334">Chiamate SIP/H.323 standard</span><span class="sxs-lookup"><span data-stu-id="6fcc1-334">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="6fcc1-335">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="6fcc1-335">Truphone Voice</span></span>
    
- <span data-ttu-id="6fcc1-336">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="6fcc1-336">TwistedPair Radio</span></span>
    
- <span data-ttu-id="6fcc1-337">Schermata di Computer Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="6fcc1-337">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="6fcc1-338">Passaggio 2: creare e configurare una cassetta postale di dati di terze parti in Office 365</span><span class="sxs-lookup"><span data-stu-id="6fcc1-338">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="6fcc1-339">Di seguito sono riportati i passaggi per la creazione e la configurazione di una cassetta postale di dati di terze parti per l'importazione di dati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-339">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="6fcc1-340">Come spiegato in precedenza, gli elementi vengono importati nella cassetta postale se il connettore partner non è in grado di mappare l'ID utente dell'elemento a un account utente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-340">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="6fcc1-341">**Completare queste attività nell'interfaccia di amministrazione di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-341">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="6fcc1-342">Creare un account utente in Office 365 e assegnargli una licenza di Exchange Online piano 2; vedere [aggiungere utenti a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-342">Create a user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="6fcc1-343">È necessaria una licenza di piano 2 per attivare il blocco per controversia legale o abilitare una cassetta postale di archiviazione con una quota illimitata.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-343">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="6fcc1-344">Aggiungere l'account utente per la cassetta postale dei dati di terze parti al ruolo **amministratore di Exchange** in Office 365; Per ulteriori informazioni, vedere [assegnare ruoli di amministratore in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-344">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6fcc1-345">Annotare le credenziali per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-345">Write down the credentials for this user account.</span></span> <span data-ttu-id="6fcc1-346">È necessario fornirle al partner, come descritto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-346">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="6fcc1-347">**Completare queste attività nell'interfaccia di amministrazione di Exchange**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-347">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="6fcc1-348">Nascondere la cassetta postale dei dati di terze parti nella rubrica e negli altri elenchi di indirizzi dell'organizzazione. vedere [gestire le cassette postali degli utenti](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-348">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="6fcc1-349">In alternativa, è possibile eseguire il comando di PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-349">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="6fcc1-350">Assegnare l'autorizzazione **FullAccess** alla cassetta postale dei dati di terze parti in modo che gli amministratori o i responsabili della conformità possano aprire la cassetta postale dei dati di terze parti nel client desktop di Outlook. vedere [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-350">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="6fcc1-351">Abilitare le seguenti funzionalità di Office 365 correlate alla conformità per la cassetta postale dei dati di terze parti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-351">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="6fcc1-352">Abilitare la cassetta postale di archiviazione; vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-352">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="6fcc1-353">In questo modo è possibile liberare spazio di archiviazione nella cassetta postale principale impostando un criterio di archiviazione che consente di spostare gli elementi di dati di terze parti nella cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-353">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="6fcc1-354">In questo modo si dispone di un'archiviazione illimitata per i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-354">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="6fcc1-355">Abilitare il blocco per controversia legale nella cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-355">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="6fcc1-356">È anche possibile applicare un criterio di conservazione di Office 365 nel centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-356">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="6fcc1-357">Se la cassetta postale viene mantenuta in attesa, gli elementi di terze parti vengono conservati (indefinitamente o per una durata specificata) e impediscono che vengano eliminati dalla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-357">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="6fcc1-358">Vedere uno dei seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-358">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="6fcc1-359">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="6fcc1-359">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="6fcc1-360">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="6fcc1-360">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    - <span data-ttu-id="6fcc1-361">Abilitare la registrazione di controllo della cassetta postale per l'accesso del proprietario, di un delegato e dell'amministratore alla cassetta postale dei dati di terze parti; vedere [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-361">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="6fcc1-362">In questo modo è possibile controllare tutte le attività eseguite da qualsiasi utente che abbia accesso alla cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-362">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="6fcc1-363">Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="6fcc1-363">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="6fcc1-364">Il passaggio successivo consiste nel configurare cassette postali degli utenti per supportare i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-364">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="6fcc1-365">Completare queste attività utilizzando l'interfaccia di amministrazione di Exchange o utilizzando i cmdlet di Windows PowerShell corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-365">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="6fcc1-366">Abilitare la cassetta postale di archiviazione per ogni utente; vedere [abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-366">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="6fcc1-367">Inserire le cassette postali degli utenti sul blocco per controversia legale o applicare un criterio di conservazione di Office 365; vedere uno dei seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-367">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="6fcc1-368">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="6fcc1-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="6fcc1-369">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="6fcc1-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="6fcc1-370">Come precedentemente illustrato, quando si abilita un blocco delle cassette postali, è possibile impostare una durata per definire quanto tempo devono essere conservati gli elementi dell'origine dati di terze parti oppure è possibile scegliere di conservare gli elementi per un periodo di tempo indeterminato.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-370">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="6fcc1-371">Passaggio 4: fornire informazioni al partner</span><span class="sxs-lookup"><span data-stu-id="6fcc1-371">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="6fcc1-372">Il passaggio finale consiste nel fornire al partner le informazioni seguenti affinché sia in grado di configurare il connettore per connettersi all'organizzazione di Office 365 e importare i dati nelle cassette postali degli utenti e nella cassetta postale dei dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-372">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="6fcc1-373">Endpoint utilizzato per la connessione al servizio di Azure in Office 365:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-373">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```text
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="6fcc1-374">Credenziali di accesso (ID utente e password di Office 365) della cassetta postale di dati di terze parti creata al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-374">The sign-in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="6fcc1-375">Queste credenziali sono necessarie affinché il connettore partner possa accedere e importare gli elementi nelle cassette postali degli utenti e nella cassetta postale di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-375">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="6fcc1-376">Passaggio 5: registrare il connettore di dati di terze parti in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6fcc1-376">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="6fcc1-377">A partire da settembre 30, 2018, il servizio di Azure in Office 365 inizierà a utilizzare l'autenticazione moderna in Exchange Online per autenticare i connettori di dati di terze parti che tentano di connettersi all'organizzazione di Office 365 per importare i dati.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-377">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="6fcc1-378">La causa di questa modifica consiste nel fatto che l'autenticazione moderna fornisce maggiore sicurezza rispetto al metodo corrente, basato sulla whitelist di connettori di terze parti che utilizzano l'endpoint descritto in precedenza per la connessione al servizio Azure.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-378">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="6fcc1-379">Per abilitare un connettore di dati di terze parti per la connessione a Office 365 utilizzando il nuovo metodo di autenticazione moderno, un amministratore dell'organizzazione di Office 365 deve acconsentire a registrare il connettore come applicazione di servizio attendibile in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-379">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="6fcc1-380">Per eseguire questa operazione, è necessario accettare una richiesta di autorizzazione per consentire al connettore di accedere ai dati dell'organizzazione in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-380">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="6fcc1-381">Dopo aver accettato la richiesta, il connettore di dati di terze parti viene aggiunto come applicazione Enterprise ad Azure Active Directory e rappresentato come entità di servizio.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-381">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="6fcc1-382">Per ulteriori informazioni sul processo di consenso, vedere [tenant admin consenso](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-382">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="6fcc1-383">Di seguito sono riportati i passaggi per accedere e accettare la richiesta di registrazione del connettore:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-383">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="6fcc1-384">Accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ed eseguire l'accesso con le credenziali di un amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-384">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span>

   <span data-ttu-id="6fcc1-385">Verrà visualizzata la finestra di dialogo seguente.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-385">The following dialog box is displayed.</span></span> <span data-ttu-id="6fcc1-386">È possibile espandere le carriere per esaminare le autorizzazioni che verranno assegnate al connettore.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-386">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Viene visualizzata la finestra di dialogo delle richieste di autorizzazione](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="6fcc1-388">Fare clic su **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-388">Click **Accept**.</span></span>

<span data-ttu-id="6fcc1-389">Dopo aver accettato la richiesta, viene visualizzato il [portale di Azure](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="6fcc1-389">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="6fcc1-390">Per visualizzare l'elenco delle applicazioni per l'organizzazione, fare clic su applicazioni di **Azure Active Directory** > **Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-390">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="6fcc1-391">Il connettore di dati di terze parti di Office 365 è elencato nel Blade **applicazioni Enterprise** .</span><span class="sxs-lookup"><span data-stu-id="6fcc1-391">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fcc1-392">Dopo il 30 settembre 2018, i dati di terze parti non verranno più importati nelle cassette postali dell'organizzazione se non si registra un connettore di dati di terze parti in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-392">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="6fcc1-393">Nota i connettori di dati di terze parti esistenti (quelli creati prima del 30 settembre 2018) devono essere registrati anche in Azure Active Directory attenendosi alla procedura descritta nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-393">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="6fcc1-394">Revoca del consenso per un connettore di dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="6fcc1-394">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="6fcc1-395">Dopo che l'organizzazione ha acconsentito alla richiesta di autorizzazione per la registrazione di un connettore di dati di terze parti in Azure Active Directory, l'organizzazione può revocare il consenso in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-395">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="6fcc1-396">Tuttavia, la revoca del consenso per un connettore significa che i dati provenienti dall'origine dati di terze parti non verranno più importati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-396">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="6fcc1-397">Per revocare il consenso per un connettore di dati di terze parti, è possibile eliminare l'applicazione (eliminando l'entità di servizio corrispondente) da Azure Active Directory utilizzando il Blade **applicazioni Enterprise** nel portale di Azure o utilizzando il [Remove-msolserviceprincipal viene](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-397">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="6fcc1-398">È inoltre possibile utilizzare il cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-398">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="6fcc1-399">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="6fcc1-399">More information</span></span>

- <span data-ttu-id="6fcc1-400">Come illustrato in precedenza, gli elementi provenienti da origini dati di terze parti vengono importati nelle cassette postali di Exchange come messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-400">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="6fcc1-401">Il connettore partner importa l'elemento utilizzando uno schema richiesto dall'API di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-401">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="6fcc1-402">Nella tabella seguente vengono descritte le proprietà del messaggio di un elemento di un'origine dati di terze parti dopo che è stato importato in una cassetta postale di Exchange come messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-402">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="6fcc1-403">Nella tabella viene indicato anche se la proprietà del messaggio è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-403">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="6fcc1-404">È necessario popolare le proprietà obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-404">Mandatory properties must be populated.</span></span> <span data-ttu-id="6fcc1-405">Se un elemento è mancante di una proprietà obbligatoria, non verrà importato in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-405">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="6fcc1-406">Il processo di importazione restituisce un messaggio di errore che spiega il motivo per cui un elemento non è stato importato e la proprietà mancante.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-406">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="6fcc1-407">**Proprietà del messaggio**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-407">**Message property**</span></span>|<span data-ttu-id="6fcc1-408">**Obbligatorio?**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-408">**Mandatory?**</span></span>|<span data-ttu-id="6fcc1-409">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-409">**Description**</span></span>|<span data-ttu-id="6fcc1-410">**Valore di esempio**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-410">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6fcc1-411">**Da**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-411">**FROM**</span></span> <br/> |<span data-ttu-id="6fcc1-412">Sì</span><span class="sxs-lookup"><span data-stu-id="6fcc1-412">Yes</span></span>  <br/> |<span data-ttu-id="6fcc1-413">L'utente che ha originariamente creato o inviato l'elemento nell'origine dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-413">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="6fcc1-414">Il connettore partner tenta di mappare l'ID utente dall'elemento di origine (ad esempio un handle Twitter) a un account utente di Office 365 per tutti i partecipanti (utenti nei campi da e a).</span><span class="sxs-lookup"><span data-stu-id="6fcc1-414">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="6fcc1-415">Verrà importata una copia del messaggio nella cassetta postale di ogni partecipante.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-415">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="6fcc1-416">Se non è possibile eseguire il mapping di nessuno dei partecipanti dall'elemento a un account utente di Office 365, l'elemento verrà importato nella cassetta postale di archiviazione di terze parti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-416">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="6fcc1-417">Il partecipante identificato come mittente dell'elemento deve disporre di una cassetta postale attiva nell'organizzazione di Office 365 in cui l'elemento viene importato.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-417">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="6fcc1-418">In caso contrario, viene restituito l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-418">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="6fcc1-419">**A**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-419">**TO**</span></span> <br/> |<span data-ttu-id="6fcc1-420">Sì</span><span class="sxs-lookup"><span data-stu-id="6fcc1-420">Yes</span></span>  <br/> |<span data-ttu-id="6fcc1-421">L'utente che ha ricevuto un elemento, se applicabile per un elemento nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-421">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="6fcc1-422">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-422">**SUBJECT**</span></span> <br/> |<span data-ttu-id="6fcc1-423">No</span><span class="sxs-lookup"><span data-stu-id="6fcc1-423">No</span></span>  <br/> |<span data-ttu-id="6fcc1-424">L'oggetto dell'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-424">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="6fcc1-425">**Data**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-425">**DATE**</span></span> <br/> |<span data-ttu-id="6fcc1-426">Sì</span><span class="sxs-lookup"><span data-stu-id="6fcc1-426">Yes</span></span>  <br/> |<span data-ttu-id="6fcc1-427">La data in cui l'elemento è stato originariamente creato o pubblicato nell'origine dati del cliente.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-427">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="6fcc1-428">Ad esempio, la data in cui un messaggio Twitter è stato tweeted.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-428">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="6fcc1-429">**CORPO**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-429">**BODY**</span></span> <br/> |<span data-ttu-id="6fcc1-430">No</span><span class="sxs-lookup"><span data-stu-id="6fcc1-430">No</span></span>  <br/> |<span data-ttu-id="6fcc1-431">Il contenuto del messaggio o del post.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-431">The contents of the message or post.</span></span> <span data-ttu-id="6fcc1-432">Per alcune origini dati, il contenuto di questa proprietà può corrispondere al contenuto della proprietà **SUBJECT**.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-432">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="6fcc1-433">Durante il processo di importazione, il connettore del partner tenta di mantenere la fedeltà completa dall'origine di contenuto il più possibile.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-433">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="6fcc1-434">Se possibile, i file, gli elementi grafici o altri contenuti del corpo dell'elemento di origine sono inclusi in questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-434">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="6fcc1-435">In caso contrario, il contenuto dell'elemento di origine è incluso nella proprietà **ATTACHMENT**.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-435">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="6fcc1-436">I contenuti di questa proprietà dipendono dal connettore del partner e dalla funzionalità della piattaforma di origine.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-436">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="6fcc1-437">**ALLEGATO**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-437">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="6fcc1-438">No</span><span class="sxs-lookup"><span data-stu-id="6fcc1-438">No</span></span>  <br/> |<span data-ttu-id="6fcc1-439">Se un elemento nell'origine dati, ad esempio un tweet in Twitter o una conversazione di messaggistica istantanea, ha un file allegato o include immagini, la connessione del partner tenterà innanzitutto di includere gli allegati nella proprietà **Body** .</span><span class="sxs-lookup"><span data-stu-id="6fcc1-439">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="6fcc1-440">Se non è possibile, allora viene aggiunto alla proprietà \* \* ATTACHMENT \* \*.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-440">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="6fcc1-441">Altri esempi di allegati sono i Like su Facebook, i metadati dell'origine del contenuto e le risposte a un messaggio o a un post.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-441">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="6fcc1-442">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="6fcc1-442">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="6fcc1-443">Sì</span><span class="sxs-lookup"><span data-stu-id="6fcc1-443">Yes</span></span>  <br/> | <span data-ttu-id="6fcc1-444">Si tratta di una proprietà multivalore, che viene creata e compilata dal connettore partner.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-444">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="6fcc1-445">Il formato di questa proprietà è `IPM.NOTE.Source.Event`.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-445">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="6fcc1-446">Questa proprietà deve iniziare con `IPM.NOTE`.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-446">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="6fcc1-447">Questo formato è simile a quello della classe `IPM.NOTE.X` Message. Questa proprietà include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-447">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="6fcc1-448">`Source`: Indica l'origine dati di terze parti; ad esempio, Twitter, Facebook o BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-448">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="6fcc1-449">`Event`: Indica il tipo di attività eseguita nell'origine dati di terze parti che ha prodotto gli elementi; ad esempio, un tweet in Twitter o un post in Facebook.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-449">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="6fcc1-450">Gli eventi sono specifici per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-450">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="6fcc1-451">Uno scopo di questa proprietà risiede nel filtrare gli elementi specifici in base all'origine dati in cui un elemento ha avuto origine o in base al tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-451">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="6fcc1-452">In una ricerca eDiscovery, ad esempio, è possibile creare una query di ricerca per trovare tutti i tweet pubblicati da un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-452">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="6fcc1-453">Quando gli elementi vengono importati correttamente nelle cassette postali di Office 365, viene restituito un identificatore univoco al chiamante come parte della risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-453">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="6fcc1-454">Questo identificatore, denominato `x-IngestionCorrelationID`, può essere utilizzato per la risoluzione dei problemi successivi da parte di partner per il monitoraggio end-to-end degli elementi.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-454">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="6fcc1-455">Si consiglia di raccogliere queste informazioni e registrarle nel modo più appropriato.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-455">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="6fcc1-456">Di seguito è riportato un esempio di una risposta HTTP che mostra l'identificatore:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-456">Here's an example of an HTTP response showing this identifier:</span></span>

    ```text
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="6fcc1-457">È possibile utilizzare lo strumento di ricerca contenuto nel centro sicurezza e conformità per cercare gli elementi importati nelle cassette postali di Office 365 da un'origine dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-457">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="6fcc1-458">Per eseguire la ricerca in modo specifico per questi elementi importati, è possibile utilizzare le seguenti coppie proprietà-valore del messaggio nella casella parola chiave per una ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-458">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="6fcc1-459">**`kind:externaldata`**: Utilizzare questa coppia proprietà-valore per eseguire la ricerca in tutti i tipi di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-459">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="6fcc1-460">Ad esempio, per cercare gli elementi importati da un'origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query `kind:externaldata AND subject:contoso`di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-460">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="6fcc1-461">**`itemclass:ipm.externaldata.<third-party data type>`**: Utilizzare questa coppia proprietà-valore per cercare solo un tipo di dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-461">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="6fcc1-462">Ad esempio, per cercare solo i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query `itemclass:ipm.externaldata.Facebook* AND subject:contoso`di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="6fcc1-462">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="6fcc1-463">Per un elenco completo dei valori da utilizzare per i tipi di dati di terze `itemclass` parti per la proprietà, vedere [utilizzare la ricerca contenuto per cercare i dati di terze parti che sono stati importati in Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="6fcc1-463">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="6fcc1-464">Per ulteriori informazioni sull'utilizzo di Ricerca contenuto e sulla creazione di query di ricerca con parole chiave, vedere:</span><span class="sxs-lookup"><span data-stu-id="6fcc1-464">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="6fcc1-465">Ricerca contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="6fcc1-465">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="6fcc1-466">Query con parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="6fcc1-466">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
