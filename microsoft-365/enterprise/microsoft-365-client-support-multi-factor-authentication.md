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
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 Supporto app client: autenticazione a più fattori

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Per fornire un ulteriore livello di sicurezza per gli accesso, i client possono essere configurati per l'utilizzo dell'autenticazione a più fattori (MFA), che utilizza sia una password utente che un altro metodo di verifica utente in base a:

- Qualcosa in loro possesso che non è facilmente duplicato, ad esempio uno smartphone.
- Qualcosa che l'utente ha in modo univoco e biologico, come le impronte digitali, il volto o un altro attributo biometrico

Ulteriori informazioni [sull'autenticazione a più fattori.](/azure/active-directory/authentication/multi-factor-authentication)

## <a name="supported-clients--platforms"></a>Client supportati & piattaforme

Le versioni più recenti dei client e delle piattaforme seguenti supportano l'autenticazione a più fattori. Per ulteriori informazioni sul supporto della piattaforma in Microsoft 365, vedere [Requisiti di sistema per Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell per SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
