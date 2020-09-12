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
description: In questo articolo viene descritto come rimuovere o disabilitare l'autenticazione moderna ibrida da Skype for business e Exchange.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547097"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Rimozione o disabilitazione dell'autenticazione moderna ibrida da Skype for Business ed Exchange

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Se è stata abilitata l'autenticazione moderna ibrida (HMA) solo per scoprire che non è adatta per l'ambiente corrente, è possibile disabilitare HMA. In questo articolo viene illustrato come.
  
## <a name="who-is-this-article-for"></a>Per chi è questo articolo?

Se è stata abilitata l'autenticazione moderna in Skype for business online o locale e/o Exchange Online o in locale e si è trovato che è necessario disabilitare HMA, questi passaggi sono disponibili per l'utente.

> [!IMPORTANT]
> Vedere l'articolo relativo alle topologie di[Skype for business supportate con l'autenticazione moderna](https://technet.microsoft.com/library/mt803262.aspx)se si è in Skype for business online o in locale, è presente una HMA a topologia mista ed è necessario esaminare le topologie supportate prima di iniziare.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Come disabilitare l'autenticazione moderna ibrida (Exchange)

1. **Exchange locale**: aprire Exchange Management Shell ed eseguire i comandi seguenti: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [connettersi a Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) con Remote PowerShell. Eseguire il seguente comando per trasformare il flag  *OAuth2ClientProfileEnabled*  su' false ':

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Come disabilitare l'autenticazione moderna ibrida (Skype for business)

1. **Skype for business locale**: eseguire i comandi seguenti in Skype for Business Management Shell:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for business online**: [connettersi a Skype for business online](manage-skype-for-business-online-with-microsoft-365-powershell.md) con Remote PowerShell. Eseguire il seguente comando per disabilitare l'autenticazione moderna:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Collegare di nuovo la panoramica dell'autenticazione moderna](hybrid-modern-auth-overview.md) . 
  

