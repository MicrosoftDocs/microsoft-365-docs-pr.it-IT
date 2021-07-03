---
title: 'Microsoft 365 Supporto app client: autenticazione a più fattori'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In questo articolo, scopri quali piattaforme, client e moduli di PowerShell supportano l'autenticazione a più fattori per Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8749c05e3f7ce5dacf7d3ed1eaa46a46a20482d5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286454"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="cb660-103">Microsoft 365 Supporto app client: autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="cb660-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="cb660-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="cb660-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cb660-105">Per fornire un ulteriore livello di sicurezza per gli accesso, i client possono essere configurati per l'utilizzo dell'autenticazione a più fattori (MFA), che utilizza sia una password utente che un altro metodo di verifica utente in base a:</span><span class="sxs-lookup"><span data-stu-id="cb660-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="cb660-106">Qualcosa in loro possesso che non è facilmente duplicato, ad esempio uno smartphone.</span><span class="sxs-lookup"><span data-stu-id="cb660-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="cb660-107">Qualcosa che l'utente ha in modo univoco e biologico, come le impronte digitali, il volto o un altro attributo biometrico</span><span class="sxs-lookup"><span data-stu-id="cb660-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="cb660-108">Ulteriori informazioni [sull'autenticazione a più fattori.](/azure/active-directory/authentication/multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="cb660-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="cb660-109">Client supportati & piattaforme</span><span class="sxs-lookup"><span data-stu-id="cb660-109">Supported clients & platforms</span></span>

<span data-ttu-id="cb660-110">Le versioni più recenti dei client e delle piattaforme seguenti supportano l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="cb660-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="cb660-111">Per ulteriori informazioni sul supporto della piattaforma in Microsoft 365, vedere [Requisiti di sistema per Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span><span class="sxs-lookup"><span data-stu-id="cb660-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="cb660-112">Moduli di PowerShell supportati</span><span class="sxs-lookup"><span data-stu-id="cb660-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="cb660-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb660-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="cb660-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb660-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="cb660-115">PowerShell per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb660-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
