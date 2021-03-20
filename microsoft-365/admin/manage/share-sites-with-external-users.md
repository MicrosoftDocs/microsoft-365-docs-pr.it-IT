---
title: Condividere siti e file con utenti guest
f1.keywords: NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 89502322-bfbb-43d6-9207-4030f8ce26e0
ROBOTS: NOINDEX
description: "Informazioni su come condividere siti e file con persone esterne all'organizzazione. "
ms.openlocfilehash: 585034580fd18d9584b4df3d0bec7026cf207f50
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915038"
---
# <a name="share-sites-and-files-with-guest-users"></a><span data-ttu-id="cef6a-103">Condividere siti e file con utenti guest</span><span class="sxs-lookup"><span data-stu-id="cef6a-103">Share sites and files with guest users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cef6a-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="cef6a-104">The admin center is changing.</span></span> <span data-ttu-id="cef6a-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="cef6a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="cef6a-106">Per collaborare con persone esterne all'organizzazione, è possibile condividere interi siti o file specifici esternamente.</span><span class="sxs-lookup"><span data-stu-id="cef6a-106">To collaborate with people outside your organization, you can share entire sites or specific files externally.</span></span> <span data-ttu-id="cef6a-107">Se si vuole passare direttamente alla configurazione della condivisione, scegliere lo scenario che si desidera attivare:</span><span class="sxs-lookup"><span data-stu-id="cef6a-107">If you want to get straight to setting up sharing, choose the scenario you want to enable:</span></span>

- [<span data-ttu-id="cef6a-108">Collaborare con gli utenti guest a un documento</span><span class="sxs-lookup"><span data-stu-id="cef6a-108">Collaborate with guests on a document</span></span>](../../solutions/collaborate-on-documents.md)
- [<span data-ttu-id="cef6a-109">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="cef6a-109">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="cef6a-110">Collaborare con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="cef6a-110">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)
  
## <a name="deciding-how-to-share-your-content"></a><span data-ttu-id="cef6a-111">Scegliere il metodo di condivisione del contenuto</span><span class="sxs-lookup"><span data-stu-id="cef6a-111">Deciding how to share your content</span></span>

<span data-ttu-id="cef6a-112">Quando si valuta se e come condividere contenuto esternamente, è opportuno considerare i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="cef6a-112">When considering if and how you want to share content externally, think about the following:</span></span>
  
- <span data-ttu-id="cef6a-113">A chi si desidera concedere l'accesso al contenuto del sito e a tutti i siti secondari e a quali elementi si desidera consentire l'accesso?</span><span class="sxs-lookup"><span data-stu-id="cef6a-113">To whom do you want to grant access to content on the site and any subsites, and what do you want them to be able to do?</span></span>
    
- <span data-ttu-id="cef6a-114">A quali membri dell'organizzazione si vuole concedere l'autorizzazione a condividere contenuto con l'esterno?</span><span class="sxs-lookup"><span data-stu-id="cef6a-114">To whom in your organization do you want to grant permission to share content externally?</span></span> 
    
- <span data-ttu-id="cef6a-115">Esiste contenuto che non deve assolutamente essere visualizzato da utenti esterni all'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="cef6a-115">Is there content you want to ensure is never available to be viewed by people external to your organization?</span></span>
    
<span data-ttu-id="cef6a-116">Rispondendo a queste domande sarà più semplice pianificare la strategia per la condivisione dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="cef6a-116">The answers to these questions will help you plan your strategy for content sharing.</span></span>
  
|<span data-ttu-id="cef6a-117">**Provare:**</span><span class="sxs-lookup"><span data-stu-id="cef6a-117">**Try this:**</span></span>|<span data-ttu-id="cef6a-118">**Per...**</span><span class="sxs-lookup"><span data-stu-id="cef6a-118">**If you need to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cef6a-119">Aggiungere un guest a un gruppo</span><span class="sxs-lookup"><span data-stu-id="cef6a-119">Add a guest to a group</span></span>  <br/> |<span data-ttu-id="cef6a-120">Fornire a un utente esterno all'organizzazione l'accesso continuo alle informazioni e al contenuto in un sito del team.</span><span class="sxs-lookup"><span data-stu-id="cef6a-120">Provide someone outside your organization with ongoing access to information and content on a team site.</span></span> <span data-ttu-id="cef6a-121">Tali utenti devono poter agire come utenti effettivi del sito creando, modificando e visualizzando il contenuto.</span><span class="sxs-lookup"><span data-stu-id="cef6a-121">They need the ability to perform like a full user of your site and create, edit, and view content.</span></span>  <br/> |
|<span data-ttu-id="cef6a-122">Condividere un documento e richiedere l'autenticazione degli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="cef6a-122">Share a document and require guests to authenticate.</span></span>  <br/> |<span data-ttu-id="cef6a-123">Fornire a persone specifiche esterne all'organizzazione l'accesso sicuro a un documento per la revisione o la collaborazione, ma queste persone non richiedono l'accesso ad altri contenuti nel sito.</span><span class="sxs-lookup"><span data-stu-id="cef6a-123">Provide specific people outside your organization with secure access to a document for review or collaboration, but these people do not require access to other content on the site.</span></span>  <br/> |
|<span data-ttu-id="cef6a-124">Condividere un documento, ma non richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="cef6a-124">Share a document, but don't require authentication.</span></span>  <br/> |<span data-ttu-id="cef6a-125">Condividere un collegamento a un documento non riservato o non confidenziale con utenti esterni all'organizzazione in modo che possano visualizzarlo o aggiornarlo con commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="cef6a-125">Share a link to a non-sensitive or non-confidential document with people outside your organization so that they can either view it or update it with feedback.</span></span> <span data-ttu-id="cef6a-126">Queste persone non richiedono l'accesso al contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="cef6a-126">These people do not require access to content on the site.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="cef6a-127">Quando si disabilita la condivisione esterna, gli utenti esterni all'organizzazione che attualmente dispongono dell'accesso non avranno più accesso.</span><span class="sxs-lookup"><span data-stu-id="cef6a-127">When you disable external sharing, people outside the organization who currently have access will no longer have access.</span></span> <span data-ttu-id="cef6a-128">Se in seguito si rieccerà la condivisione esterna, l'accesso verrà ripristinato per queste persone.</span><span class="sxs-lookup"><span data-stu-id="cef6a-128">If you later turn external sharing back on, access will be restored for these people.</span></span> <span data-ttu-id="cef6a-129">Per impedire a un utente di accedere a un contenuto condiviso, rimuoverlo dal gruppo [di Microsoft 365,](/office365/admin/create-groups/add-or-remove-members-from-groups)rimuovere le autorizzazioni dal sito o interrompere la condivisione del file o della [cartella con essi.](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323)</span><span class="sxs-lookup"><span data-stu-id="cef6a-129">To prevent a user from accessing a shared content, [remove them from the Microsoft 365 group](/office365/admin/create-groups/add-or-remove-members-from-groups), remove their permissions from the site, or [stop sharing the file or folder with them](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323).</span></span> 
  
## <a name="enable-external-sharing-at-the-organization-level"></a><span data-ttu-id="cef6a-130">Abilitare la condivisione esterna a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="cef6a-130">Enable external sharing at the organization level</span></span>

<span data-ttu-id="cef6a-131">La condivisione esterna è attivata per impostazione predefinita a livello di organizzazione, ma non per tutti i nuovi siti.</span><span class="sxs-lookup"><span data-stu-id="cef6a-131">External sharing is turned on by default at the organization level, but not for all new sites.</span></span> <span data-ttu-id="cef6a-132">Per info, vedi [Panoramica della condivisione esterna.](/sharepoint/external-sharing-overview)</span><span class="sxs-lookup"><span data-stu-id="cef6a-132">For info, see [External sharing overview](/sharepoint/external-sharing-overview).</span></span> 

> [!NOTE]
>  <span data-ttu-id="cef6a-133">Per consentire la condivisione esterna per qualsiasi sito, è necessario consentirla a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cef6a-133">To allow external sharing for any site, you need to allow it at the organization level.</span></span> 
  
1. <span data-ttu-id="cef6a-134">[Nell'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339)digitare "esterno" nella casella di ricerca nella home page e scegliere Condivisione esterna **siti**.</span><span class="sxs-lookup"><span data-stu-id="cef6a-134">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), type "external" in the search box on the Home page, and choose **Sites external sharing**.</span></span>
  
2. <span data-ttu-id="cef6a-135">Nella pagina visualizzata scegliere se gli utenti possono condividere solo con utenti guest esistenti, utenti guest nuovi ed esistenti o con chiunque.</span><span class="sxs-lookup"><span data-stu-id="cef6a-135">On the page that opens, choose whether users can share with existing guests only, new and existing guests, or anyone.</span></span> 
    
3. <span data-ttu-id="cef6a-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cef6a-136">Select **Save**.</span></span>
    
<span data-ttu-id="cef6a-137">Dopo aver abilitato la condivisione esterna a livello di organizzazione, è possibile ottimizzare le impostazioni di condivisione per disabilitare la condivisione esterna per siti specifici.</span><span class="sxs-lookup"><span data-stu-id="cef6a-137">After you enable external sharing at the organization level, you can fine tune your sharing settings to disable external sharing for particular sites.</span></span> <span data-ttu-id="cef6a-138">Per info, vedi [Attivare o disattivare la condivisione esterna per un sito.](/sharepoint/change-external-sharing-site)</span><span class="sxs-lookup"><span data-stu-id="cef6a-138">For info, see [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
  

  

