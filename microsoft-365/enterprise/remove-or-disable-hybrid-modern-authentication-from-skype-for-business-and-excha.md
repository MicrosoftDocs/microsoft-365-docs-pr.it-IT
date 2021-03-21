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
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927289"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Rimozione o disabilitazione dell'autenticazione moderna ibrida da Skype for Business ed Exchange

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Se l'autenticazione moderna ibrida (HMA) è stata abilitata solo per trovare che non è idonea per l'ambiente corrente, è possibile disabilitare HMA. Questo articolo spiega come.
  
## <a name="who-is-this-article-for"></a>Per chi è disponibile questo articolo?

Se è stata abilitata l'autenticazione moderna in Skype for Business online o in locale e/o Exchange Online o locale e si è riscontrato che è necessario disabilitare HMA, questi passaggi sono per te.

> [!IMPORTANT]
> Vedere l'articolo '[Topologie di Skype for Business](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)supportate con l'autenticazione moderna ' se si è in Skype for Business online o in locale, si dispone di un HMA a topologia mista ed è necessario esaminare le topologie supportate prima di iniziare.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Come disabilitare l'autenticazione moderna ibrida (Exchange)

1. **Exchange locale**: aprire Exchange Management Shell ed eseguire i comandi seguenti: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online:** [connettersi a Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) con Remote PowerShell. Eseguire il comando seguente per impostare il flag  *OAuth2ClientProfileEnabled*  su "false":

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Come disabilitare l'autenticazione moderna ibrida (Skype for Business)

1. **Skype for Business locale**: Eseguire i comandi seguenti in Skype for Business Management Shell:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for Business online:** [connettersi a Skype for Business online](manage-skype-for-business-online-with-microsoft-365-powershell.md) con Remote PowerShell. Eseguire il comando seguente per disabilitare l'autenticazione moderna:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Collegamento alla panoramica dell'autenticazione moderna.](hybrid-modern-auth-overview.md) 
