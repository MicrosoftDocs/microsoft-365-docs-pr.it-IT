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
description: In questo articolo vengono descritti i limiti nel caso di eDiscovery di base in Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311425"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="dad12-103">Limiti in Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="dad12-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="dad12-104">Nella tabella seguente sono elencati i limiti per i casi principali di eDiscovery e i blocchi associati a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="dad12-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="dad12-105">Per ulteriori informazioni su Core eDiscovery, vedere [Overview of Core eDiscovery.](./get-started-core-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="dad12-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="dad12-106">Descrizione del limite</span><span class="sxs-lookup"><span data-stu-id="dad12-106">Description of limit</span></span> | <span data-ttu-id="dad12-107">Limite</span><span class="sxs-lookup"><span data-stu-id="dad12-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="dad12-108">Numero massimo di casi per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dad12-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="dad12-109">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="dad12-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="dad12-110">Numero massimo di blocchi di maiuscole e minuscole per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dad12-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="dad12-111">10,000</span><span class="sxs-lookup"><span data-stu-id="dad12-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="dad12-112">Numero massimo di cassette postali in un singolo caso di blocco.</span><span class="sxs-lookup"><span data-stu-id="dad12-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="dad12-113">Questo limite include il totale combinato delle cassette postali degli utenti e le cassette postali associate Microsoft 365 gruppi, Microsoft Teams e Yammer gruppi.</span><span class="sxs-lookup"><span data-stu-id="dad12-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="dad12-114">1,000</span><span class="sxs-lookup"><span data-stu-id="dad12-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="dad12-115">Numero massimo di siti in un singolo caso di blocco.</span><span class="sxs-lookup"><span data-stu-id="dad12-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="dad12-116">Questo limite include il totale combinato di OneDrive for Business, siti SharePoint e siti associati a Microsoft 365 Groups, Microsoft Teams e Yammer Groups.</span><span class="sxs-lookup"><span data-stu-id="dad12-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="dad12-117">100</span><span class="sxs-lookup"><span data-stu-id="dad12-117">100</span></span>  <br/> |
  |<span data-ttu-id="dad12-118">Numero massimo di casi visualizzati nella home page principale di eDiscovery e numero massimo di elementi visualizzati nelle schede Esenzioni, Ricerche ed Esportazione all'interno di un caso.</span><span class="sxs-lookup"><span data-stu-id="dad12-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="dad12-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dad12-119"><sup>1</sup></span></span> |<span data-ttu-id="dad12-120">1,000</span><span class="sxs-lookup"><span data-stu-id="dad12-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="dad12-121"><sup>1</sup> Per visualizzare un elenco di più di 1.000 casi, blocchi, ricerche o esportazioni, è possibile utilizzare i cmdlet di PowerShell Office 365 Security & Compliance corrispondenti:</span><span class="sxs-lookup"><span data-stu-id="dad12-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="dad12-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="dad12-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="dad12-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="dad12-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="dad12-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="dad12-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="dad12-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="dad12-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="dad12-126">Per ulteriori informazioni sui limiti relativi alle ricerche e alle esportazioni associate a un caso di eDiscovery di base, vedere [Limits for Content search e Core eDiscovery.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="dad12-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>