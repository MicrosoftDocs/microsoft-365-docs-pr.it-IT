---
title: 'Supporto delle app client Microsoft 365: Sign-On singoli'
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
description: In questo articolo vengono fornite informazioni sulle piattaforme, i client e i moduli di PowerShell che supportano il servizio Single Sign-on per Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b70f0c1ec4a6e94651b987830c8b29993732a3c2
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806665"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Supporto delle app client Microsoft 365: Sign-On singoli

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Single Sign-on (SSO) aggiunge la sicurezza e la convenienza quando gli utenti eseguono l'accesso alle applicazioni in Azure Active Directory. Con Single Sign-on, gli utenti accedono una volta con un account per accedere ai dispositivi di servizi di dominio Active Directory (AD DS), software as a Service (SaaS) e applicazioni Web locali.

Per ulteriori informazioni, vedere [Single Sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-clients--platforms"></a>Client supportati & piattaforme

Le versioni più recenti dei client e delle piattaforme seguenti supportano il servizio Single Sign-on. Per ulteriori informazioni sul supporto delle piattaforme in Microsoft 365, vedere [requisiti di sistema per microsoft 365](https://products.office.com/office-system-requirements).
<br>
<br>

| Client | Android | iOS | Mac| Windows 10 <br> App moderne| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Portale aziendale | N/D | ![Supportato](../media/check-mark.png) | Pianificata | ![Supportato](../media/check-mark.png) | N/D |
| Cortana | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Delve | Pianificata | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Edge | ![Supportato](../media/check-mark.png) | Pianificata | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Excel | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Kaizala | ![Supportato](../media/check-mark.png) | Pianificata | N/D | N/D | N/D |
| Office Lens| ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Office Mobile | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Portale di Office | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| OneDrive | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | Pianificata | ![Supportato](../media/check-mark.png) | Pianificata |
| OneNote | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | Pianificata |
| Outlook | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | Pianificata | ![Supportato](../media/check-mark.png) |
| Planner | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power Apps | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | Pianificata | N/D |
| Automatizzare la potenza | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | Pianificata |
| PowerPoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Skype for Business | Pianificata | Pianificata | N/D | N/D | N/D |
| SharePoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Sticky Notes | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Stream | Pianificata | Pianificata | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Teams | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | Pianificata | N/D | Pianificata |
| Da fare | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Visio | N/D | ![Supportato](../media/check-mark.png) | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Whiteboard | N/D | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Word | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Yammer | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | Pianificata |

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

- [PowerShell di Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell per SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
