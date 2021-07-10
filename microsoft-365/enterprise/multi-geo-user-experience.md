---
title: Esperienza utente in ambiente multi-geografico.
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Informazioni sull'esperienza utente riguardo SharePoint e OneDrive in ambiente multi-geografico per Microsoft 365.
ms.openlocfilehash: 4e752581f4ca692f9fecc5019f8e34543ebf7067
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362379"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="f62cd-103">Esperienza utente in ambiente multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="f62cd-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="f62cd-104">Ecco cosa gli utenti visualizzeranno in una configurazione OneDrive Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="f62cd-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="f62cd-105">Cassette postali di Exchange</span><span class="sxs-lookup"><span data-stu-id="f62cd-105">Exchange mailbox</span></span>

<span data-ttu-id="f62cd-106">Viene effettuato il provisioning della cassetta postale di Exchange dell'utente alla posizione dati preferita e viene spostata automaticamente se viene modificato il PDL.</span><span class="sxs-lookup"><span data-stu-id="f62cd-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="f62cd-107">Gli utenti possono usare normalmente Outlook e Outlook sul web senza alcun cambiamento nell’esperienza utente in un ambiente multi-geo.</span><span class="sxs-lookup"><span data-stu-id="f62cd-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="f62cd-108">Siti hub</span><span class="sxs-lookup"><span data-stu-id="f62cd-108">Hub sites</span></span>

<span data-ttu-id="f62cd-109">I siti hub di SharePoint migliorano l'individuazione e l’interesse per il contenuto dei dipendenti, creando una rappresentazione completa e coerente di progetti, reparti e aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="f62cd-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="f62cd-110">In un ambiente multi-geo, siti da posizioni satellite possono essere facilmente associati con un sito hub indipendentemente dalla sua posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="f62cd-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="f62cd-111">Gli utenti possono eseguire ricerche e ottenere risultati attraverso l'hub con una singola ricerca, indipendentemente dalla posizione geografica dei siti.</span><span class="sxs-lookup"><span data-stu-id="f62cd-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="f62cd-112">Icona di avvio delle app di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f62cd-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="f62cd-113">L’icona di avvio delle app funziona con il multi-geo e indirizza ogni riquadro verso la posizione geografica appropriata del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f62cd-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="f62cd-114">I riquadri di SharePoint e OneDrive indirizzeranno l'utente verso la località corrispondente alla posizione geografica predisposta per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f62cd-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="f62cd-115">Questo significa che se l'utente ha un OneDrive nella posizione centrale, il riquadro SharePoint lo indirizzerà verso SP Home nella posizione centrale, ma sarà effettuato il provisioning del sito del gruppo nella posizione corrispondente al proprio PDL.</span><span class="sxs-lookup"><span data-stu-id="f62cd-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="f62cd-116">Applicazioni di Office</span><span class="sxs-lookup"><span data-stu-id="f62cd-116">Office applications</span></span>

<span data-ttu-id="f62cd-117">Office applicazioni quali Word, Excel e PowerPoint rileveranno automaticamente la posizione geografica OneDrive corretta per ogni utente al momento dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="f62cd-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive geo-location for each user when they log in.</span></span> <span data-ttu-id="f62cd-118">Non è necessario immettere l'URL geo-specifico per i siti di OneDrive o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f62cd-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-sync-app"></a><span data-ttu-id="f62cd-119">sincronizzazione OneDrive app</span><span class="sxs-lookup"><span data-stu-id="f62cd-119">OneDrive sync app</span></span>

<span data-ttu-id="f62cd-120">L'app sincronizzazione OneDrive (versione 17.3.6943.0625 e versioni successive) rileverà automaticamente la posizione OneDrive geografica corretta per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f62cd-120">The OneDrive sync app (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive geo location for the user.</span></span> <span data-ttu-id="f62cd-121">Il supporto dell'app di sincronizzazione include la possibilità di sincronizzare i siti basati su gruppi indipendentemente dalla posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="f62cd-121">Sync app support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="f62cd-122">Si noti che il client di sincronizzazione Groove non è supportato per multi-geo.</span><span class="sxs-lookup"><span data-stu-id="f62cd-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-location"></a><span data-ttu-id="f62cd-123">OneDrive percorso</span><span class="sxs-lookup"><span data-stu-id="f62cd-123">OneDrive location</span></span>

<span data-ttu-id="f62cd-124">Gli utenti avranno la propria OneDrive il provisioning nella posizione dati preferita.</span><span class="sxs-lookup"><span data-stu-id="f62cd-124">Users will have their OneDrive provisioned in their preferred data location.</span></span> <span data-ttu-id="f62cd-125">Se un utente passa a un URL di OneDrive che contiene una posizione geografica errata (ad esempio un segnalibro da una posizione geografica precedente), viene reindirizzato automaticamente al OneDrive nella posizione geografica appropriata.</span><span class="sxs-lookup"><span data-stu-id="f62cd-125">If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="f62cd-126">OneDrive per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="f62cd-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="f62cd-p107">L'app OneDrive per dispositivi mobili iOS e Android illustra i file di OneDrive e i file condivisi con l'utente indipendentemente dalla posizione geografica. La ricerca dalle app OneDrive mostra risultati pertinenti da tutte le posizioni geografiche. Scaricare la versione più recente di tali applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f62cd-p107">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location. Search from the OneDrive mobile apps will show relevant results from all geo locations. Please download the latest version of these apps.</span></span>

<span data-ttu-id="f62cd-130">Vedere [Usare OneDrive in iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) e [Usare OneDrive in Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="f62cd-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="f62cd-131">OneDrive Mobile Client</span><span class="sxs-lookup"><span data-stu-id="f62cd-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="f62cd-132">Il OneDrive Mobile Client è predisposto per multi-geo e mostrerà il contenuto pertinente e i risultati di tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="f62cd-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="f62cd-133">Ricerca</span><span class="sxs-lookup"><span data-stu-id="f62cd-133">Search</span></span>

<span data-ttu-id="f62cd-134">Ogni posizione geografica dispone di un proprio indice di ricerca e centro ricerche.</span><span class="sxs-lookup"><span data-stu-id="f62cd-134">Each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="f62cd-135">Quando un utente esegue una ricerca, la query viene inviata a tutte le posizioni geografiche e i risultati restituiti vengono uniti e quindi classificati in modo che l'utente ose ottiene risultati unificati.</span><span class="sxs-lookup"><span data-stu-id="f62cd-135">When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results.</span></span> <span data-ttu-id="f62cd-136">Gli utenti ottengono risultati da tutte le posizioni geografiche indipendentemente dalla propria posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="f62cd-136">Users get results from all geo locations regardless of their own geo location.</span></span> <span data-ttu-id="f62cd-137">Vedere [Configure Search for OneDrive Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span><span class="sxs-lookup"><span data-stu-id="f62cd-137">See [Configure Search for OneDrive Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="f62cd-138">Di seguito sono elencati i client di ricerca supportati:</span><span class="sxs-lookup"><span data-stu-id="f62cd-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="f62cd-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f62cd-139">OneDrive</span></span>

-   <span data-ttu-id="f62cd-140">Delve</span><span class="sxs-lookup"><span data-stu-id="f62cd-140">Delve</span></span>

-   <span data-ttu-id="f62cd-141">Home page di SharePoint</span><span class="sxs-lookup"><span data-stu-id="f62cd-141">SharePoint Home</span></span>

-   <span data-ttu-id="f62cd-142">Centro ricerche</span><span class="sxs-lookup"><span data-stu-id="f62cd-142">The Search Center</span></span>

-   <span data-ttu-id="f62cd-143">Applicazioni di ricerca personalizzate che utilizzano l'API del servizio di ricerca di SharePoint</span><span class="sxs-lookup"><span data-stu-id="f62cd-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="f62cd-144">Home page di SharePoint</span><span class="sxs-lookup"><span data-stu-id="f62cd-144">SharePoint Home</span></span> 

<span data-ttu-id="f62cd-145">In SharePoint Multi-Geo la SharePoint è ospitata nella posizione in cui risiede l'utente, come determinato dalla OneDrive locale.</span><span class="sxs-lookup"><span data-stu-id="f62cd-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive location.</span></span> <span data-ttu-id="f62cd-146">Ad esempio: se il OneDrive dell'utente è ospitato in una posizione satellite europea, verrà visualizzata la home page di SharePoint dall’Europa.</span><span class="sxs-lookup"><span data-stu-id="f62cd-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="f62cd-147">Home page di SharePoint include tutti i contenuti pertinenti per l'utente indipendentemente dalla posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="f62cd-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="f62cd-148">**Siti seguiti, notizie dai siti, siti recenti, siti frequenti e siti suggeriti**</span><span class="sxs-lookup"><span data-stu-id="f62cd-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="f62cd-149">Tutti questi componenti verranno visualizzati dall'utente indipendentemente dall'area geografica in cui è ospitato il contenuto, purché si disponga delle autorizzazioni per tale contenuto.</span><span class="sxs-lookup"><span data-stu-id="f62cd-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="f62cd-150">**Collegamenti alle funzionalità**</span><span class="sxs-lookup"><span data-stu-id="f62cd-150">**Features Links**</span></span>

<span data-ttu-id="f62cd-151">Gli amministratori possono configurare i collegamenti alle funzionalità nella home page di SharePoint in base alle esigenze per ogni posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="f62cd-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="f62cd-152">In questo modo l'amministratore potrà inserire nella home page di SP di ogni area geografica il collegamenti appropriati per gli utenti di quella regione.</span><span class="sxs-lookup"><span data-stu-id="f62cd-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="f62cd-153">SharePoint Mobile Client</span><span class="sxs-lookup"><span data-stu-id="f62cd-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="f62cd-154">Il SharePoint Mobile Client è predisposto per multi-geo e mostrerà il contenuto pertinente e i risultati da tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="f62cd-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="f62cd-155">Condivisione</span><span class="sxs-lookup"><span data-stu-id="f62cd-155">Sharing</span></span>

<span data-ttu-id="f62cd-156">L'esperienza di Selezione Utenti mostra tutti gli utenti indipendentemente dalla posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="f62cd-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="f62cd-157">Questo consente a un utente di condividere con un altro utente nella stessa posizione geografica o in qualsiasi altra località geografica del tenant.</span><span class="sxs-lookup"><span data-stu-id="f62cd-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="f62cd-158">Il contenuto di diverse posizioni geografiche verrà visualizzato nella visualizzazione Condivisi con **l'utente** corrente nel OneDrive dell'utente ed è possibile accedervi con l'esperienza single Sign-On indipendentemente dalla posizione geografica in cui è ospitato.</span><span class="sxs-lookup"><span data-stu-id="f62cd-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="f62cd-159">Funzionalità di Teams</span><span class="sxs-lookup"><span data-stu-id="f62cd-159">Teams Experience</span></span>

<span data-ttu-id="f62cd-160">Teams è un servizio multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="f62cd-160">Teams is a multi-geo service.</span></span> <span data-ttu-id="f62cd-161">Indipendentemente dalla posizione geografica dell'utente vengono visualizzati i file di OneDrive e i file recenti.</span><span class="sxs-lookup"><span data-stu-id="f62cd-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="f62cd-162">Menzioni @ funziona con utenti provenienti da tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="f62cd-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="f62cd-163">Profili utente</span><span class="sxs-lookup"><span data-stu-id="f62cd-163">User profiles</span></span>

<span data-ttu-id="f62cd-p113">Le informazioni sul profilo utente sono gestite nella posizione geografica dell'utente. Quando si seleziona un utente, si verrà indirizzati alla posizione geografica corretta per l'utente, in cui sarà possibile visualizzare i dettagli del profilo completo.</span><span class="sxs-lookup"><span data-stu-id="f62cd-p113">User profile information is mastered in the user's geo location. When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="f62cd-166">Se Delve è disattivato, verrà visualizzata l'esperienza del profilo classico in SharePoint, il quale non ha funzionalità Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="f62cd-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


