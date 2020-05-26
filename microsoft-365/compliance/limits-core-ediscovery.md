---
title: Limiti nel caso di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 00df8cff683701ce5ee38dca12b6f7af5b31c8b0
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351897"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="edaee-103">Limiti in eDiscovery di base</span><span class="sxs-lookup"><span data-stu-id="edaee-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="edaee-104">Nella tabella seguente sono elencati i limiti per i casi di eDiscovery di base e le esenzioni associate a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="edaee-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="edaee-105">Per ulteriori informazioni su eDiscovery di base, vedere [Overview of core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="edaee-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="edaee-106">**Descrizione del limite**</span><span class="sxs-lookup"><span data-stu-id="edaee-106">**Description of limit**</span></span>|<span data-ttu-id="edaee-107">**Tipo di limite**</span><span class="sxs-lookup"><span data-stu-id="edaee-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="edaee-108">Numero massimo di casi per un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="edaee-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="edaee-109">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="edaee-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="edaee-110">Numero massimo di case conservate per un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="edaee-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="edaee-111">10.000</span><span class="sxs-lookup"><span data-stu-id="edaee-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="edaee-112">Numero massimo di cassette postali in un singolo blocco maiuscole/minuscole</span><span class="sxs-lookup"><span data-stu-id="edaee-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="edaee-113">1.000</span><span class="sxs-lookup"><span data-stu-id="edaee-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="edaee-114">Numero massimo di siti di SharePoint e OneDrive for business in un unico blocco del caso</span><span class="sxs-lookup"><span data-stu-id="edaee-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="edaee-115">100</span><span class="sxs-lookup"><span data-stu-id="edaee-115">100</span></span>  <br/> |
  |<span data-ttu-id="edaee-116">Numero massimo di casi visualizzati nella Home page di eDiscovery principale e il numero massimo di elementi visualizzati nelle schede esenzioni, ricerche ed esportazione all'interno di un caso.</span><span class="sxs-lookup"><span data-stu-id="edaee-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="edaee-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="edaee-117"><sup>1</sup></span></span> |<span data-ttu-id="edaee-118">1.000</span><span class="sxs-lookup"><span data-stu-id="edaee-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="edaee-119"><sup>1</sup> per visualizzare un elenco di più di 1.000 casi, esenzioni, ricerche o esportazioni, è possibile utilizzare il cmdlet di PowerShell per la sicurezza & conformità corrispondente di Office 365:</span><span class="sxs-lookup"><span data-stu-id="edaee-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="edaee-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="edaee-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [<span data-ttu-id="edaee-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="edaee-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [<span data-ttu-id="edaee-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="edaee-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [<span data-ttu-id="edaee-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="edaee-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
