---
title: 'Supporto app client Microsoft 365: autenticazione a più fattori'
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
description: In questo articolo vengono apprese le piattaforme, i client e i moduli di PowerShell che supportano l'autenticazione a più fattori per Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097469"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Supporto app client Microsoft 365: autenticazione a più fattori

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Per fornire un ulteriore livello di sicurezza per gli accesso, i client possono essere configurati per l'utilizzo dell'autenticazione a più fattori (MFA), che utilizza sia una password utente che un metodo di verifica utente aggiuntivo basato su:

- Qualcosa in loro possesso che non è facilmente duplicato, ad esempio uno smartphone.
- Qualcosa che l'utente ha in modo univoco e biondo, ad esempio le impronte digitali, il volto o un altro attributo biometrico

Ulteriori informazioni [sull'autenticazione a più fattori.](/azure/active-directory/authentication/multi-factor-authentication)

## <a name="supported-clients--platforms"></a>Client supportati & piattaforme

Le versioni più recenti dei client e delle piattaforme seguenti supportano l'autenticazione a più fattori. Per ulteriori informazioni sul supporto della piattaforma in Microsoft 365, vedere Requisiti di [sistema per Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
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
| Power Automate | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| PowerPoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Skype for Business | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) |
| Amministratore di Skype for Business | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
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