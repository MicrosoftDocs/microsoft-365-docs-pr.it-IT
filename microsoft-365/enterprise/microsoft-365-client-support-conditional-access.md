---
title: 'Microsoft 365 Supporto app client: accesso condizionale'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: In questo articolo, scopri quali piattaforme, client e moduli di PowerShell supportano l'Access per Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 763380429b8643c5dd01971117fccb040a9a0210
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286562"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="9b1b9-103">Microsoft 365 Supporto app client: accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="9b1b9-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="9b1b9-104">Nell'ambiente di lavoro moderno, gli utenti possono accedere alle risorse dell'organizzazione usando vari dispositivi e app da qualsiasi luogo.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="9b1b9-105">Di conseguenza, concentrarsi solo su chi può accedere a una risorsa non è più sufficiente.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="9b1b9-106">L'organizzazione deve inoltre supportare come e dove si accede a una risorsa nell'infrastruttura di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="9b1b9-107">Con Azure Active Directory, la posizione e l'accesso condizionale basato sull'autenticazione a più fattori, è possibile soddisfare questo nuovo requisito.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="9b1b9-108">L'accesso condizionale è una funzionalità di Azure Active Directory che consente di applicare controlli sull'accesso alle app nell'ambiente, il tutto in base a condizioni specifiche e gestito da una posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="9b1b9-109">Ulteriori informazioni [sull'Azure Active Directory condizionale](/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="9b1b9-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="9b1b9-110">Client supportati & piattaforme</span><span class="sxs-lookup"><span data-stu-id="9b1b9-110">Supported clients & platforms</span></span>

<span data-ttu-id="9b1b9-111">Le versioni più recenti dei client e delle piattaforme seguenti supportano l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="9b1b9-112">Per ulteriori informazioni sul supporto della piattaforma in Microsoft 365, vedere [Requisiti di sistema per Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span><span class="sxs-lookup"><span data-stu-id="9b1b9-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="9b1b9-113">Moduli di PowerShell supportati</span><span class="sxs-lookup"><span data-stu-id="9b1b9-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="9b1b9-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b1b9-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="9b1b9-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b1b9-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="9b1b9-116">PowerShell per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9b1b9-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
