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
ms.openlocfilehash: c94fc5569a5444ca6361712f57460cf0c977b18e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691113"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="a3690-103">Esperienza utente in ambiente multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="a3690-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="a3690-104">Ecco cosa gli utenti visualizzeranno in una configurazione OneDrive Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="a3690-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="a3690-105">Cassette postali di Exchange</span><span class="sxs-lookup"><span data-stu-id="a3690-105">Exchange mailbox</span></span>

<span data-ttu-id="a3690-106">Viene effettuato il provisioning della cassetta postale di Exchange dell'utente alla posizione dati preferita e viene spostata automaticamente se viene modificato il PDL.</span><span class="sxs-lookup"><span data-stu-id="a3690-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="a3690-107">Gli utenti possono usare normalmente Outlook e Outlook sul web senza alcun cambiamento nell’esperienza utente in un ambiente multi-geo.</span><span class="sxs-lookup"><span data-stu-id="a3690-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="a3690-108">Siti hub</span><span class="sxs-lookup"><span data-stu-id="a3690-108">Hub sites</span></span>

<span data-ttu-id="a3690-109">I siti hub di SharePoint migliorano l'individuazione e l’interesse per il contenuto dei dipendenti, creando una rappresentazione completa e coerente di progetti, reparti e aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="a3690-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="a3690-110">In un ambiente multi-geo, siti da posizioni satellite possono essere facilmente associati con un sito hub indipendentemente dalla sua posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="a3690-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="a3690-111">Gli utenti possono eseguire ricerche e ottenere risultati attraverso l'hub con una singola ricerca, indipendentemente dalla posizione geografica dei siti.</span><span class="sxs-lookup"><span data-stu-id="a3690-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="a3690-112">Icona di avvio delle app di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3690-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="a3690-113">L’icona di avvio delle app funziona con il multi-geo e indirizza ogni riquadro verso la posizione geografica appropriata del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a3690-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="a3690-114">I riquadri di SharePoint e OneDrive indirizzeranno l'utente verso la località corrispondente alla posizione geografica predisposta per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a3690-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="a3690-115">Questo significa che se l'utente ha un OneDrive nella posizione centrale, il riquadro SharePoint lo indirizzerà verso SP Home nella posizione centrale, ma sarà effettuato il provisioning del sito del gruppo nella posizione corrispondente al proprio PDL.</span><span class="sxs-lookup"><span data-stu-id="a3690-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="a3690-116">Applicazioni di Office</span><span class="sxs-lookup"><span data-stu-id="a3690-116">Office applications</span></span>

<span data-ttu-id="a3690-117">Le applicazioni Office come Word, Excel e PowerPoint rileveranno automaticamente la posizione geografica corretta di OneDrive for Business per ciascun utente al momento dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="a3690-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive for Business geo-location for each user when they log in.</span></span> <span data-ttu-id="a3690-118">Non è necessario immettere l'URL geo-specifico per i siti di OneDrive o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a3690-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-for-business-sync-client"></a><span data-ttu-id="a3690-119">Client di sincronizzazione OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a3690-119">OneDrive for Business Sync Client</span></span>

<span data-ttu-id="a3690-120">Il client di sincronizzazione OneDrive for Business (versione 17.3.6943.0625 e successive) rileverà automaticamente la posizione geografica corretta di OneDrive for Business per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a3690-120">The OneDrive for Business Sync Client (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive for Business geo location for the user.</span></span> <span data-ttu-id="a3690-121">Il supporto dei client di sincronizzazione consente di sincronizzare i siti basati su gruppi indipendentemente dalla posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="a3690-121">Synch client support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="a3690-122">Si noti che il client di sincronizzazione Groove non è supportato per multi-geo.</span><span class="sxs-lookup"><span data-stu-id="a3690-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-for-business-location"></a><span data-ttu-id="a3690-123">Posizione di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a3690-123">OneDrive for Business location</span></span>

<span data-ttu-id="a3690-p106">Gli utenti disporranno di OneDrive for Business fornito nel percorso dati preferito. Se un utente accede a un URL OneDrive che contiene una posizione geografica errata (come un segnalibro da una precedente posizione geografica), viene automaticamente reindirizzato a OneDrive nella posizione geografica appropriata.</span><span class="sxs-lookup"><span data-stu-id="a3690-p106">Users will have their OneDrive for Business provisioned in their preferred data location. If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="a3690-126">OneDrive per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="a3690-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="a3690-p107">L'app OneDrive per dispositivi mobili iOS e Android illustra i file di OneDrive e i file condivisi con l'utente indipendentemente dalla posizione geografica. La ricerca dalle app OneDrive mostra risultati pertinenti da tutte le posizioni geografiche. Scaricare la versione più recente di tali applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a3690-p107">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location. Search from the OneDrive mobile apps will show relevant results from all geo locations. Please download the latest version of these apps.</span></span>

<span data-ttu-id="a3690-130">Vedere [Usare OneDrive in iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) e [Usare OneDrive in Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="a3690-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="a3690-131">OneDrive Mobile Client</span><span class="sxs-lookup"><span data-stu-id="a3690-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="a3690-132">Il OneDrive Mobile Client è predisposto per multi-geo e mostrerà il contenuto pertinente e i risultati di tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="a3690-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="a3690-133">Ricerca</span><span class="sxs-lookup"><span data-stu-id="a3690-133">Search</span></span>

<span data-ttu-id="a3690-p108">Ogni posizione geografica ha un proprio indice di ricerca e Centro ricerche. Quando si esegue la ricerca, la query viene inviata a tutte le posizioni geografiche e i risultati restituiti vengono uniti e quindi classificati in modo che l'utente ottenga risultati unificati. Gli utenti ottengono risultati da tutte le località geografiche indipendentemente dalla posizione geografica. Vedere [Configurare la ricerca di OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="a3690-p108">Each geo location has its own search index and Search Center. When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results. Users get results from all geo locations regardless of their own geo location. See [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="a3690-138">Di seguito sono elencati i client di ricerca supportati:</span><span class="sxs-lookup"><span data-stu-id="a3690-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="a3690-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a3690-139">OneDrive for Business</span></span>

-   <span data-ttu-id="a3690-140">Delve</span><span class="sxs-lookup"><span data-stu-id="a3690-140">Delve</span></span>

-   <span data-ttu-id="a3690-141">Home page di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a3690-141">SharePoint Home</span></span>

-   <span data-ttu-id="a3690-142">Centro ricerche</span><span class="sxs-lookup"><span data-stu-id="a3690-142">The Search Center</span></span>

-   <span data-ttu-id="a3690-143">Applicazioni di ricerca personalizzate che utilizzano l'API del servizio di ricerca di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a3690-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="a3690-144">Home page di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a3690-144">SharePoint Home</span></span> 

<span data-ttu-id="a3690-145">In SharePoint Multi-Geo, la home page di SharePoint è ospitata nella posizione in cui l'utente si trova, in base alla sua posizione in OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="a3690-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive for business location.</span></span> <span data-ttu-id="a3690-146">Ad esempio: se il OneDrive dell'utente è ospitato in una posizione satellite europea, verrà visualizzata la home page di SharePoint dall’Europa.</span><span class="sxs-lookup"><span data-stu-id="a3690-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="a3690-147">Home page di SharePoint include tutti i contenuti pertinenti per l'utente indipendentemente dalla posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="a3690-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="a3690-148">**Siti seguiti, notizie dai siti, siti recenti, siti frequenti e siti suggeriti**</span><span class="sxs-lookup"><span data-stu-id="a3690-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="a3690-149">Tutti questi componenti verranno visualizzati dall'utente indipendentemente dall'area geografica in cui è ospitato il contenuto, purché si disponga delle autorizzazioni per tale contenuto.</span><span class="sxs-lookup"><span data-stu-id="a3690-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="a3690-150">**Collegamenti alle funzionalità**</span><span class="sxs-lookup"><span data-stu-id="a3690-150">**Features Links**</span></span>

<span data-ttu-id="a3690-151">Gli amministratori possono configurare i collegamenti alle funzionalità nella home page di SharePoint in base alle esigenze per ogni posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="a3690-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="a3690-152">In questo modo l'amministratore potrà inserire nella home page di SP di ogni area geografica il collegamenti appropriati per gli utenti di quella regione.</span><span class="sxs-lookup"><span data-stu-id="a3690-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="a3690-153">SharePoint Mobile Client</span><span class="sxs-lookup"><span data-stu-id="a3690-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="a3690-154">Il SharePoint Mobile Client è predisposto per multi-geo e mostrerà il contenuto pertinente e i risultati da tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="a3690-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="a3690-155">Condivisione</span><span class="sxs-lookup"><span data-stu-id="a3690-155">Sharing</span></span>

<span data-ttu-id="a3690-156">L'esperienza di Selezione Utenti mostra tutti gli utenti indipendentemente dalla posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="a3690-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="a3690-157">Questo consente a un utente di condividere con un altro utente nella stessa posizione geografica o in qualsiasi altra località geografica del tenant.</span><span class="sxs-lookup"><span data-stu-id="a3690-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="a3690-158">Il contenuto sarà visualizzato da posizioni geografiche diverse nella visualizzazione **Condivisi con me** del OneDrive for Business dell’utente ed è accessibile tramite l’esperienza Single Sign-On indipendentemente da quale posizione geografica è ospitato.</span><span class="sxs-lookup"><span data-stu-id="a3690-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive for Business and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="a3690-159">Funzionalità di Teams</span><span class="sxs-lookup"><span data-stu-id="a3690-159">Teams Experience</span></span>

<span data-ttu-id="a3690-160">Teams funziona con Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="a3690-160">Teams is multi-geo aware.</span></span> <span data-ttu-id="a3690-161">Indipendentemente dalla posizione geografica dell'utente vengono visualizzati i file di OneDrive e i file recenti.</span><span class="sxs-lookup"><span data-stu-id="a3690-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="a3690-162">Menzioni @ funziona con utenti provenienti da tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="a3690-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="a3690-163">Profili utente</span><span class="sxs-lookup"><span data-stu-id="a3690-163">User profiles</span></span>

<span data-ttu-id="a3690-p113">Le informazioni sul profilo utente sono gestite nella posizione geografica dell'utente. Quando si seleziona un utente, si verrà indirizzati alla posizione geografica corretta per l'utente, in cui sarà possibile visualizzare i dettagli del profilo completo.</span><span class="sxs-lookup"><span data-stu-id="a3690-p113">User profile information is mastered in the user's geo location. When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="a3690-166">Se Delve è disattivato, verrà visualizzata l'esperienza del profilo classico in SharePoint, il quale non ha funzionalità Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="a3690-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


