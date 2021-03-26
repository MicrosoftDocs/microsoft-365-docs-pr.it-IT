---
title: Usare PowerShell per creare report per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: "Riepilogo: usare PowerShell per Microsoft 365 per creare report che non è possibile produrre nell'interfaccia di amministrazione di Microsoft 365."
ms.openlocfilehash: dc183ae8a315bf788befc85474d0647802ac91ee
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222780"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="a3ffa-103">Usare PowerShell per creare report per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3ffa-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="a3ffa-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a3ffa-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a3ffa-105">Nell'interfaccia di amministrazione di Microsoft 365 sono disponibili molti report diversi.</span><span class="sxs-lookup"><span data-stu-id="a3ffa-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a3ffa-106">Tuttavia, questi report forniscono solo così tante informazioni e a volte ne servono di più.</span><span class="sxs-lookup"><span data-stu-id="a3ffa-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="a3ffa-107">Questo è il momento in cui è necessario PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3ffa-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="a3ffa-108">Questi articoli descrivono come usare PowerShell per Microsoft 365 per ottenere informazioni dal tenant di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="a3ffa-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="a3ffa-109">Introduzione alla creazione di report con PowerShell per Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="a3ffa-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="a3ffa-110">Perché è necessario usare PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3ffa-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="a3ffa-111">Report degli account utente e delle licenze:</span><span class="sxs-lookup"><span data-stu-id="a3ffa-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="a3ffa-112">Visualizzare le licenze e i servizi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3ffa-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="a3ffa-113">Visualizzare gli utenti con licenza e senza licenza di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3ffa-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="a3ffa-114">Visualizzare i dettagli del servizio e della licenza dell'account di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3ffa-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="a3ffa-115">Visualizzare gli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3ffa-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="a3ffa-116">Report di SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a3ffa-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="a3ffa-117">Guida introduttiva a SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="a3ffa-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="a3ffa-118">Get-SPOSiteGroup - Ottiene tutti i gruppi in una raccolta siti specificata</span><span class="sxs-lookup"><span data-stu-id="a3ffa-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="a3ffa-119">Report di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a3ffa-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="a3ffa-120">Utilizzare PowerShell di Exchange Online per visualizzare la cassetta postale</span><span class="sxs-lookup"><span data-stu-id="a3ffa-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="a3ffa-121">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="a3ffa-121">Related articlesl</span></span>

[<span data-ttu-id="a3ffa-122">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3ffa-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a3ffa-123">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3ffa-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a3ffa-124">Gestire SharePoint con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3ffa-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a3ffa-125">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3ffa-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
