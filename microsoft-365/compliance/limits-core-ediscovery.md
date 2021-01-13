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
description: In questo articolo vengono descritti i limiti in core eDiscovery case in Microsoft 365.
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799663"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="a33cd-103">Limiti in eDiscovery di base</span><span class="sxs-lookup"><span data-stu-id="a33cd-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="a33cd-104">Nella tabella seguente sono elencati i limiti per i casi di eDiscovery di base e le esenzioni associate a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="a33cd-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="a33cd-105">Per ulteriori informazioni su eDiscovery di base, vedere [Overview of core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="a33cd-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="a33cd-106">Descrizione del limite</span><span class="sxs-lookup"><span data-stu-id="a33cd-106">Description of limit</span></span> | <span data-ttu-id="a33cd-107">Limite</span><span class="sxs-lookup"><span data-stu-id="a33cd-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="a33cd-108">Numero massimo di casi per un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a33cd-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="a33cd-109">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="a33cd-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="a33cd-110">Numero massimo di case conservate per un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a33cd-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="a33cd-111">10.000</span><span class="sxs-lookup"><span data-stu-id="a33cd-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="a33cd-112">Numero massimo di cassette postali in un singolo blocco maiuscole/minuscole</span><span class="sxs-lookup"><span data-stu-id="a33cd-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="a33cd-113">1,000</span><span class="sxs-lookup"><span data-stu-id="a33cd-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="a33cd-114">Numero massimo di siti di SharePoint e OneDrive for business in un unico blocco del caso</span><span class="sxs-lookup"><span data-stu-id="a33cd-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="a33cd-115">100</span><span class="sxs-lookup"><span data-stu-id="a33cd-115">100</span></span>  <br/> |
  |<span data-ttu-id="a33cd-116">Numero massimo di casi visualizzati nella Home page di eDiscovery principale e il numero massimo di elementi visualizzati nelle schede esenzioni, ricerche ed esportazione all'interno di un caso.</span><span class="sxs-lookup"><span data-stu-id="a33cd-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="a33cd-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a33cd-117"><sup>1</sup></span></span> |<span data-ttu-id="a33cd-118">1,000</span><span class="sxs-lookup"><span data-stu-id="a33cd-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="a33cd-119"><sup>1</sup> per visualizzare un elenco di più di 1.000 casi, esenzioni, ricerche o esportazioni, è possibile utilizzare i cmdlet di PowerShell per la sicurezza & conformità corrispondenti di Office 365:</span><span class="sxs-lookup"><span data-stu-id="a33cd-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="a33cd-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="a33cd-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="a33cd-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="a33cd-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="a33cd-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a33cd-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="a33cd-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="a33cd-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="a33cd-124">Per ulteriori informazioni sui limiti relativi alle ricerche di contenuto e alle esportazioni associate a un caso di eDiscovery di base, vedere [limits for content search and core eDiscovery](limits-for-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="a33cd-124">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>