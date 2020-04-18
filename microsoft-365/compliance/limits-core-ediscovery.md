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
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551449"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="34b5e-103">Limiti in eDiscovery di base</span><span class="sxs-lookup"><span data-stu-id="34b5e-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="34b5e-104">Nella tabella seguente sono elencati i limiti per i casi di eDiscovery di base e le esenzioni associate a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="34b5e-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="34b5e-105">Per ulteriori informazioni su eDiscovery di base, vedere [Overview of core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="34b5e-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="34b5e-106">**Descrizione del limite**</span><span class="sxs-lookup"><span data-stu-id="34b5e-106">**Description of limit**</span></span>|<span data-ttu-id="34b5e-107">**Tipo di limite**</span><span class="sxs-lookup"><span data-stu-id="34b5e-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="34b5e-108">Numero massimo di casi per un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="34b5e-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="34b5e-109">Nessun limite</span><span class="sxs-lookup"><span data-stu-id="34b5e-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="34b5e-110">Numero massimo di case conservate per un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="34b5e-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="34b5e-111">10.000</span><span class="sxs-lookup"><span data-stu-id="34b5e-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="34b5e-112">Numero massimo di cassette postali in un singolo blocco maiuscole/minuscole</span><span class="sxs-lookup"><span data-stu-id="34b5e-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="34b5e-113">1.000</span><span class="sxs-lookup"><span data-stu-id="34b5e-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="34b5e-114">Numero massimo di siti di SharePoint e OneDrive for business in un unico blocco del caso</span><span class="sxs-lookup"><span data-stu-id="34b5e-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="34b5e-115">100</span><span class="sxs-lookup"><span data-stu-id="34b5e-115">100</span></span>  <br/> |
  |<span data-ttu-id="34b5e-116">Numero massimo di casi visualizzati nella Home page di eDiscovery principale e il numero massimo di elementi visualizzati nelle schede esenzioni, ricerche ed esportazione all'interno di un caso.</span><span class="sxs-lookup"><span data-stu-id="34b5e-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="34b5e-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="34b5e-117"><sup>1</sup></span></span> |<span data-ttu-id="34b5e-118">1.000</span><span class="sxs-lookup"><span data-stu-id="34b5e-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="34b5e-119"><sup>1</sup> per visualizzare un elenco di più di 1.000 casi, esenzioni, ricerche o esportazioni, è possibile utilizzare il cmdlet di PowerShell per la sicurezza & conformità corrispondente di Office 365:</span><span class="sxs-lookup"><span data-stu-id="34b5e-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="34b5e-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="34b5e-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [<span data-ttu-id="34b5e-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="34b5e-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [<span data-ttu-id="34b5e-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="34b5e-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [<span data-ttu-id="34b5e-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="34b5e-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
