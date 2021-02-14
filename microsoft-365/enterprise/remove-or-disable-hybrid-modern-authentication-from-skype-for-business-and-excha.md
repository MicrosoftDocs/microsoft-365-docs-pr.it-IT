---
title: Rimozione o disabilitazione dell'autenticazione moderna ibrida da Skype for Business ed Exchange
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Questo articolo spiega come rimuovere o disabilitare l'autenticazione moderna ibrida da Skype for Business ed Exchange.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547097"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="e3184-103">Rimozione o disabilitazione dell'autenticazione moderna ibrida da Skype for Business ed Exchange</span><span class="sxs-lookup"><span data-stu-id="e3184-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="e3184-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="e3184-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e3184-105">Se l'autenticazione moderna ibrida (HMA) è stata abilitata solo per trovarla non idonea per l'ambiente corrente, è possibile disabilitare HMA.</span><span class="sxs-lookup"><span data-stu-id="e3184-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="e3184-106">Questo articolo spiega come.</span><span class="sxs-lookup"><span data-stu-id="e3184-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="e3184-107">A chi è fatto questo articolo?</span><span class="sxs-lookup"><span data-stu-id="e3184-107">Who is this article for?</span></span>

<span data-ttu-id="e3184-108">Se è stata abilitata l'autenticazione moderna in Skype for Business online o locale e/o Exchange Online o locale e si è trovato che è necessario disabilitare HMA, questi passaggi sono per te.</span><span class="sxs-lookup"><span data-stu-id="e3184-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3184-109">Vedere l'articolo " Topologie di[Skype for Business](https://technet.microsoft.com/library/mt803262.aspx)supportate con l'autenticazione moderna" se si è in Skype for Business online o in locale, si dispone di una topologia mista HMA ed è necessario esaminare le topologie supportate prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="e3184-109">See the '[Skype for Business topologies supported with Modern Authentication](https://technet.microsoft.com/library/mt803262.aspx)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="e3184-110">Come disabilitare l'autenticazione moderna ibrida (Exchange)</span><span class="sxs-lookup"><span data-stu-id="e3184-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="e3184-111">**Exchange locale**: aprire Exchange Management Shell ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3184-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="e3184-112">**Exchange Online:** [connettersi a Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) con Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3184-112">**Exchange Online**: [Connect to Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="e3184-113">Eseguire il comando seguente per impostare il flag  *OAuth2ClientProfileEnabled*  su "false":</span><span class="sxs-lookup"><span data-stu-id="e3184-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="e3184-114">Come disabilitare l'autenticazione moderna ibrida (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="e3184-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="e3184-115">**Skype for Business locale**: Eseguire i seguenti comandi in Skype for Business Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e3184-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="e3184-116">**Skype for Business online:** [connettersi a Skype for Business online](manage-skype-for-business-online-with-microsoft-365-powershell.md) con Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3184-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="e3184-117">Eseguire il comando seguente per disabilitare l'autenticazione moderna:</span><span class="sxs-lookup"><span data-stu-id="e3184-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="e3184-118">[Collegamento alla panoramica dell'autenticazione moderna.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e3184-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
  

