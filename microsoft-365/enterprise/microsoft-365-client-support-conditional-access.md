---
title: 'Supporto delle app client di Microsoft 365: accesso condizionale'
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
description: In questo articolo vengono apprese le piattaforme, i client e i moduli di PowerShell che supportano l'accesso condizionale per Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 969dd9d712fe124458273144b3e7974e03ade9e0
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097247"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Supporto delle app client di Microsoft 365: accesso condizionale

Nell'ambiente di lavoro moderno, gli utenti possono accedere alle risorse dell'organizzazione usando vari dispositivi e app da qualsiasi luogo. Di conseguenza, concentrarsi solo su chi può accedere a una risorsa non è più sufficiente. L'organizzazione deve inoltre supportare come e dove accedere a una risorsa nell'infrastruttura di controllo di accesso.

Con il dispositivo, la posizione e l'accesso condizionale basato sull'autenticazione a più fattori di Azure Active Directory, è possibile soddisfare questo nuovo requisito. L'accesso condizionale è una funzionalità di Azure Active Directory che consente di applicare controlli sull'accesso alle app nel proprio ambiente, il tutto in base a condizioni specifiche e gestito da una posizione centrale.

Ulteriori informazioni [sull'accesso condizionale di Azure Active Directory.](/azure/active-directory/conditional-access/)

## <a name="supported-clients--platforms"></a>Client supportati & piattaforme

Le versioni più recenti dei client e delle piattaforme seguenti supportano l'accesso condizionale. Per ulteriori informazioni sul supporto della piattaforma in Microsoft 365, vedere Requisiti di [sistema per Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)

<br>
<br>

| Client | Android | iOS | Mac| Windows 10 <br> App moderne| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Amministratore di Azure Active Directory | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Access | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Amministratore di Azure | N/D | N/D | N/D | N/D | N/D |
| Portale aziendale | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D |
| Cortana | Pianificato | Pianificato | N/D | ![Supportato](../media/check-mark.png) | N/D |
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
| Power Apps | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | Pianificato | N/D |
| Power Automate | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| PowerPoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Skype for Business | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D ||
| SharePoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Amministratore di SharePoint Online | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Sticky Notes | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Stream | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Teams | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) |
| To Do | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D |
| Visio | N/D | ![Supportato](../media/check-mark.png) | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Whiteboard | Pianificato | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Word | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Analisi dell'area di lavoro | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell per SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
