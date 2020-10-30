---
title: 'Supporto delle app client Microsoft 365: autenticazione moderna'
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
description: In questo articolo vengono fornite informazioni sulle piattaforme, i client e i moduli di PowerShell che supportano l'autenticazione moderna per Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 290a151e127b05e984b9d262c3b429b561201545
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806666"
---
# <a name="microsoft-365-client-app-support-modern-authentication"></a>Supporto delle app client Microsoft 365: autenticazione moderna

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

L'autenticazione moderna Abilita l'accesso basato sulla libreria di autenticazione di Active Directory (ADAL) per le app client di Office su diverse piattaforme. Ciò consente di abilitare le funzionalità di accesso, ad esempio l'autenticazione a più fattori, la smart card e l'autenticazione basata su certificato.

Per ulteriori informazioni, vedere autenticazione a più [fattori](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) e [autenticazione basata su certificati](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Client supportati & piattaforme

Le versioni più recenti dei client e delle piattaforme seguenti supportano l'autenticazione moderna. Per ulteriori informazioni sul supporto delle piattaforme in Microsoft 365, vedere [requisiti di sistema per microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Client | Android | iOS | Mac| Windows 10 <br> App moderne| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Amministratore di Azure Active Directory | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Access | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Amministratore di Azure | N/D | N/D | N/D | N/D | N/D |
| Portale aziendale | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D |
| Cortana | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Delve | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Edge | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Excel | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Amministratore di Exchange Online | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Forms | N/D | N/D | N/D | N/D | N/D |
| Amministratore di Office 365 | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |  |
| Kaizala | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Office Mobile | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Portale di Office | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| OneDrive | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| OneNote | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Outlook | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Planner | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power Apps | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Automatizzare la potenza | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| PowerPoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Skype for Business | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) |
| Amministratore di Skype for business | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| SharePoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Amministratore di SharePoint Online | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Sticky Notes | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Stream | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Teams | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) |
| Da fare | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D |
| Visio | N/D | ![Supportato](../media/check-mark.png) | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Whiteboard | Pianificata | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Word | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Analisi del luogo di lavoro | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

- [PowerShell di Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell per SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)