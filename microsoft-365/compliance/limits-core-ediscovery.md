---
title: Limiti nel caso di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Questo articolo descrive i limiti nel caso di eDiscovery di base in Microsoft 365.
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423447"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="12487-103">Limiti in Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="12487-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="12487-104">Nella tabella seguente sono elencati i limiti per i casi principali di eDiscovery e i blocchi associati a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="12487-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="12487-105">Per ulteriori informazioni su Core eDiscovery, vedere [Panoramica di Core eDiscovery.](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="12487-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="12487-106">Descrizione del limite</span><span class="sxs-lookup"><span data-stu-id="12487-106">Description of limit</span></span> | <span data-ttu-id="12487-107">Limite</span><span class="sxs-lookup"><span data-stu-id="12487-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="12487-108">Numero massimo di casi per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="12487-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="12487-109">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="12487-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="12487-110">Numero massimo di blocchi dei casi per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="12487-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="12487-111">10.000</span><span class="sxs-lookup"><span data-stu-id="12487-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="12487-112">Numero massimo di cassette postali in un singolo blocco caso.</span><span class="sxs-lookup"><span data-stu-id="12487-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="12487-113">Questo limite include il totale combinato delle cassette postali degli utenti e le cassette postali associate ai gruppi di Microsoft 365, Microsoft Teams e Gruppi di Yammer.</span><span class="sxs-lookup"><span data-stu-id="12487-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="12487-114">1.000</span><span class="sxs-lookup"><span data-stu-id="12487-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="12487-115">Numero massimo di siti in un blocco caso singolo.</span><span class="sxs-lookup"><span data-stu-id="12487-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="12487-116">Questo limite include il totale combinato dei siti di OneDrive for Business, dei siti di SharePoint e dei siti associati a Gruppi di Microsoft 365, Microsoft Teams e Gruppi di Yammer.</span><span class="sxs-lookup"><span data-stu-id="12487-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="12487-117">100</span><span class="sxs-lookup"><span data-stu-id="12487-117">100</span></span>  <br/> |
  |<span data-ttu-id="12487-118">Numero massimo di casi visualizzati nella home page principale di eDiscovery e numero massimo di elementi visualizzati nelle schede Esenzioni, Ricerche ed Esportazione all'interno di un caso.</span><span class="sxs-lookup"><span data-stu-id="12487-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="12487-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="12487-119"><sup>1</sup></span></span> |<span data-ttu-id="12487-120">1.000</span><span class="sxs-lookup"><span data-stu-id="12487-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="12487-121"><sup>1</sup> Per visualizzare un elenco di più di 1.000 casi, blocchi, ricerche o esportazioni, è possibile utilizzare i cmdlet di PowerShell per la sicurezza & e la conformità di Office 365:</span><span class="sxs-lookup"><span data-stu-id="12487-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="12487-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="12487-122">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="12487-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="12487-123">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="12487-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="12487-124">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="12487-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="12487-125">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="12487-126">Per ulteriori informazioni sui limiti relativi alle ricerche di contenuto e alle esportazioni associate a un caso di eDiscovery di base, vedere [Limits for Content Search and Core eDiscovery.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="12487-126">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>