---
title: Eseguire una ricerca nel registro di controllo per l'attività di utenti e amministratori
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MOE150
- MET150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: "Il registro di controllo è un log di controllo unificato. Perché usare un log di controllo unificato? Poiché gli eventi provenienti dalla maggior parte dei servizi sottoscritti dall'organizzazione vengono registrati in un singolo log di controllo in cui è possibile eseguire la ricerca. Questo significa che è possibile cercare l'attività di utenti e amministratori in questi servizi:"
ms.openlocfilehash: 3cc76b272516c0e0508c7d76f0b93da44effa487
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943645"
---
# <a name="search-the-audit-log-for-user-and-admin-activity"></a><span data-ttu-id="481fa-106">Eseguire una ricerca nel registro di controllo per l'attività di utenti e amministratori</span><span class="sxs-lookup"><span data-stu-id="481fa-106">Search the audit log for user and admin activity</span></span>

<span data-ttu-id="481fa-107">Il registro di controllo è un log di controllo unificato.</span><span class="sxs-lookup"><span data-stu-id="481fa-107">The audit log is a unified audit log.</span></span> <span data-ttu-id="481fa-108">Perché usare un log di controllo unificato?</span><span class="sxs-lookup"><span data-stu-id="481fa-108">Why a unified audit log?</span></span> <span data-ttu-id="481fa-109">Poiché gli eventi provenienti dalla maggior parte dei servizi a cui si sta effettuando la sottoscrizione vengono registrati in un singolo log di controllo che è possibile cercare.</span><span class="sxs-lookup"><span data-stu-id="481fa-109">Because events from most services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="481fa-110">Questo significa che è possibile cercare l'attività di utenti e amministratori in questi servizi:</span><span class="sxs-lookup"><span data-stu-id="481fa-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="481fa-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="481fa-111">SharePoint</span></span>
- <span data-ttu-id="481fa-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="481fa-112">OneDrive</span></span>
- <span data-ttu-id="481fa-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="481fa-113">Exchange</span></span>
- <span data-ttu-id="481fa-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="481fa-114">Azure Active Directory</span></span>
- <span data-ttu-id="481fa-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="481fa-115">Microsoft Teams</span></span>
- <span data-ttu-id="481fa-116">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="481fa-116">eDiscovery</span></span>
- <span data-ttu-id="481fa-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="481fa-117">Power BI</span></span>
- <span data-ttu-id="481fa-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="481fa-118">Yammer</span></span>
- <span data-ttu-id="481fa-119">Sway</span><span class="sxs-lookup"><span data-stu-id="481fa-119">Sway</span></span>
- <span data-ttu-id="481fa-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="481fa-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="481fa-121">Configurare il controllo</span><span class="sxs-lookup"><span data-stu-id="481fa-121">Set up auditing</span></span>
  
<span data-ttu-id="481fa-122">Prima di eseguire la ricerca nel registro di controllo, è necessario eseguire alcune operazioni.</span><span class="sxs-lookup"><span data-stu-id="481fa-122">There's few things you have to do before you can search the audit log.</span></span>
  
- <span data-ttu-id="481fa-123">[Attivare la ricerca del registro di controllo](turn-audit-log-search-on-or-off.md) per avviare la registrazione di eventi che è possibile cercare</span><span class="sxs-lookup"><span data-stu-id="481fa-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="481fa-124">[Abilitare il controllo delle cassette postali](enable-mailbox-auditing.md) in modo da poter cercare gli eventi relativi alle cassette postali. ad esempio, quando un utente accede alla propria cassetta postale o Elimina gli elementi dalla cartella elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="481fa-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="481fa-125">Eseguire ricerche nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="481fa-125">Search the audit log</span></span>
  
<span data-ttu-id="481fa-126">Dopo aver attivato il controllo, è possibile eseguire la ricerca di centinaia di singoli tipi di eventi provenienti da più servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="481fa-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Microsoft 365 services.</span></span>
  
- <span data-ttu-id="481fa-127">[Eseguire una ricerca nel registro di controllo per le](search-the-audit-log-in-security-and-compliance.md) attività di utenti e amministratori</span><span class="sxs-lookup"><span data-stu-id="481fa-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="481fa-128">[Comprendere le proprietà dettagliate](detailed-properties-in-the-office-365-audit-log.md) di ogni record di controllo incluso nei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="481fa-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="481fa-129">[Ricerca di attività correlate a eDiscovery](search-for-ediscovery-activities-in-the-audit-log.md) eseguite da amministratori e responsabili della conformità</span><span class="sxs-lookup"><span data-stu-id="481fa-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
