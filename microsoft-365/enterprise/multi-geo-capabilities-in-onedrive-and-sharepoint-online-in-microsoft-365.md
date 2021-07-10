---
title: Multi-Geo Capabilities in OneDrive e SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Con Multi-Geo Capabilities in OneDrive Online l'organizzazione può espandere la propria presenza Microsoft 365 a più paesi/aree geografiche.
ms.openlocfilehash: 405f876317a6cec6defdf3f1a49b0dc32ac0add2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362283"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="33c20-103">Multi-Geo Capabilities in OneDrive e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="33c20-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="33c20-104">Le funzionalità multi-geografiche in OneDrive e SharePoint Online consentono il controllo delle risorse condivise come i siti del team di SharePoint e le cassette postali di Microsoft 365 Group archiviate in una posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="33c20-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a specified geo location.</span></span>

<span data-ttu-id="33c20-105">Ogni utente, ogni cassetta postale di Gruppi e ogni sito SharePoint ha una posizione dei dati preferita che indica la posizione geografica in cui i dati associati vengono archiviati.</span><span class="sxs-lookup"><span data-stu-id="33c20-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="33c20-106">I dati personali degli utenti (cassetta postale di Exchange e OneDrive) insieme ai siti SharePoint o ai gruppi di Microsoft 365 creati, possono essere archiviati nella posizione geografica specificata per soddisfare i requisiti di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="33c20-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="33c20-107">È possibile [specificare amministratori diversi per ogni posizione geografica](add-a-sharepoint-geo-admin.md).</span><span class="sxs-lookup"><span data-stu-id="33c20-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="33c20-108">In questo modo gli utenti avranno un’esperienza uniforme quando usano i servizi di Microsoft 365, incluse le applicazioni Office, OneDrive e Search.</span><span class="sxs-lookup"><span data-stu-id="33c20-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="33c20-109">Per i dettagli vedere [Esperienza utente in un ambiente multi-geografico](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="33c20-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="33c20-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="33c20-110">OneDrive</span></span>

<span data-ttu-id="33c20-111">Ogni utente di OneDrive può essere gestito o [spostato da un amministratore](move-onedrive-between-geo-locations.md) in una posizione satellite in base alla propria posizione dei dati preferita.</span><span class="sxs-lookup"><span data-stu-id="33c20-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="33c20-112">I file personali vengono quindi mantenuti in tale posizione geografica, ma possono essere condivisi con utenti di altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="33c20-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="33c20-113">Gruppi e siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="33c20-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="33c20-114">La gestione della funzionalità Multi-Geo è disponibile tramite l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="33c20-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="33c20-115">Per informazioni dettagliate, vedere il [post del blog corrispondente](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span><span class="sxs-lookup"><span data-stu-id="33c20-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="33c20-116">Quando un utente crea un sito connesso a un gruppo di SharePoint in un ambiente multi-geografico, la posizione preferita dei dati viene usata per determinare la posizione geografica in cui viene creato il sito e la relativa cassetta postale di Gruppi.</span><span class="sxs-lookup"><span data-stu-id="33c20-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="33c20-117">Se la posizione dei dati preferita dell'utente non è stata impostata o è stata impostata una posizione geografica non configurata come satellite, il sito e la cassetta postale vengono creati nella posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="33c20-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="33c20-118">Microsoft 365 servizi diversi da Exchange, OneDrive, SharePoint e Teams non sono Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="33c20-118">Microsoft 365 services other than Exchange, OneDrive, SharePoint, and Teams are not Multi-Geo.</span></span> <span data-ttu-id="33c20-119">Tuttavia, Microsoft 365 i gruppi creati da questi servizi verranno configurati con il file PDL del creatore e la relativa cassetta postale del gruppo Exchange, SharePoint viene eseguito il provisioning del sito nel sito geografico corrispondente.</span><span class="sxs-lookup"><span data-stu-id="33c20-119">However, Microsoft 365 Groups that are created by these services will be configured with the PDL of the creator and their Exchange Group mailbox, SharePoint site are provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="33c20-120">Gestione dell'ambiente multi-geografico</span><span class="sxs-lookup"><span data-stu-id="33c20-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="33c20-121">La configurazione e la gestione dell'ambiente multi-geo vengono eseguite tramite l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="33c20-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![Schermata della pagina con le località geografiche nell'interfaccia di amministrazione di SharePoint](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="33c20-123">Per alcune azioni, come il trasferimento di un sito di SharePoint o OneDrive, è necessario Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33c20-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="33c20-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33c20-124">See also</span></span>

[<span data-ttu-id="33c20-125">Multi-Geo in gruppi di SharePoint e Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33c20-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="33c20-126">Amministrare un ambiente multi-geo</span><span class="sxs-lookup"><span data-stu-id="33c20-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="33c20-127">Quote di archiviazione di SharePoint in ambienti multi-geo </span><span class="sxs-lookup"><span data-stu-id="33c20-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="33c20-128">Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geo</span><span class="sxs-lookup"><span data-stu-id="33c20-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
