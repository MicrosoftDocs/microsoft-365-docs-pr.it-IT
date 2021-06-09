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
description: In questo articolo viene illustrato come rimuovere o disabilitare l'autenticazione moderna ibrida Skype for Business e Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927289"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="3329e-103">Rimozione o disabilitazione dell'autenticazione moderna ibrida da Skype for Business ed Exchange</span><span class="sxs-lookup"><span data-stu-id="3329e-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="3329e-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="3329e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3329e-105">Se l'autenticazione moderna ibrida (HMA) è stata abilitata solo per trovare che non è idonea per l'ambiente corrente, è possibile disabilitare HMA.</span><span class="sxs-lookup"><span data-stu-id="3329e-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="3329e-106">Questo articolo spiega come.</span><span class="sxs-lookup"><span data-stu-id="3329e-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="3329e-107">Who questo articolo?</span><span class="sxs-lookup"><span data-stu-id="3329e-107">Who is this article for?</span></span>

<span data-ttu-id="3329e-108">Se è stata abilitata l'autenticazione moderna in Skype for Business Online o locale e/o Exchange Online o in locale e si è riscontrato che è necessario disabilitare HMA, questi passaggi sono per te.</span><span class="sxs-lookup"><span data-stu-id="3329e-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3329e-109">Vedere l'articolo ' topologie di[Skype for Business](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)supportate con l'autenticazione moderna ' se si è in Skype for Business Online o in locale, si dispone di un HMA a topologia mista ed è necessario esaminare le topologie supportate prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="3329e-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="3329e-110">Come disabilitare l'autenticazione moderna ibrida (Exchange)</span><span class="sxs-lookup"><span data-stu-id="3329e-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="3329e-111">**Exchange locale**: aprire Exchange Management Shell ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3329e-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="3329e-112">**Exchange Online**: [Connessione da Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) con Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3329e-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="3329e-113">Eseguire il comando seguente per impostare il flag  *OAuth2ClientProfileEnabled*  su "false":</span><span class="sxs-lookup"><span data-stu-id="3329e-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="3329e-114">Come disabilitare l'autenticazione moderna ibrida (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="3329e-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="3329e-115">**Skype for Business locale**: Eseguire i comandi seguenti in Skype for Business Management Shell:</span><span class="sxs-lookup"><span data-stu-id="3329e-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="3329e-116">**Skype for Business Online**: [Connessione per Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) con Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3329e-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="3329e-117">Eseguire il comando seguente per disabilitare l'autenticazione moderna:</span><span class="sxs-lookup"><span data-stu-id="3329e-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="3329e-118">[Collegamento alla panoramica dell'autenticazione moderna.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3329e-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
