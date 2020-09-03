---
title: Supporto delle app client Microsoft 365-autenticazione moderna
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
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
ms.openlocfilehash: 3e771ce5630053ffec2bf325e88b75f9a0d6baaa
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332065"
---
# <a name="microsoft-365-client-app-support---modern-authentication"></a>Supporto delle app client Microsoft 365-autenticazione moderna

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

L'autenticazione moderna Abilita l'accesso basato sulla libreria di autenticazione di Active Directory (ADAL) per le app client di Office su diverse piattaforme. Ciò consente di abilitare le funzionalità di accesso, ad esempio l'autenticazione a più fattori, la smart card e l'autenticazione basata su certificato.

Per ulteriori informazioni, vedere autenticazione a più [fattori](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) e [autenticazione basata su certificati](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started).

## <a name="supported-platforms"></a>Piattaforme supportate

 - Desktop di Windows 10
 - App di Windows 10 moderne
 - Web browser<sup>1</sup>
 - Android<sup>2</sup>
 - iOS
 - macOS

Per ulteriori informazioni sul supporto delle piattaforme in Microsoft 365, vedere [requisiti di sistema per microsoft 365](https://products.office.com/office-system-requirements).

## <a name="supported-clients"></a>Client supportati

Le versioni più recenti dei client seguenti supportano l'autenticazione moderna:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Icona Access](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Icona di Azure](../media/o365-azure-64x64.png) <br> [Portale di Azure <br>](https://azure.microsoft.com/features/azure-portal/) | ![Icona portale aziendale](../media/o365-microsoft-64x64.png) <br> [<br>Portale aziendale](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Icona di approfondimento](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Icona Dynamics 365](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) 
| ![Icona del server perimetrale](../media/o365-edge-64x64.png) <br> [Edge](https://www.microsoft.com/windows/microsoft-edge) | ![Icona Excel](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Icona maschere](../media/o365-forms-64x64.png) <br> [Maschere](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | ![Icona di Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Icona Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) 
| ![Icona di amministrazione di Office 365](../media/o365-o365admin-64x64.png) <br> [Microsoft 365 <br> amministratore](https://products.office.com/business/manage-office-365-admin-app) | ![Icona dell'obiettivo](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Icona di OneDrive for business](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) |  ![Icona di OneNote](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Icona di Outlook](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) 
| ![Icona Planner](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Icona di PowerApps](../media/o365-powerapps-64x64.png) <br> [PowerApps ](https://powerapps.microsoft.com) | ![Icona Power automatizzate](../media/o365-flow-64x64.png) <br> [<br>Automatizzare la potenza](https://flow.microsoft.com) | ![Icona PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com)| ![Icona PowerPoint](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Icona progetto](../media/o365-project-64x64.png) <br> [Progetto](https://products.office.com/project) | ![Icona di Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![Icona di SharePoint](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) | ![Icona di Skype for Business](../media/o365-skypeforbusiness-64x64.png) <br> [Skype for <br> business<sup>1</sup>](https://www.skype.com/business/) | ![Icona di StaffHub](../media/o365-staffhub-64x64.png) <br> [StaffHub](https://products.office.com/microsoft-staffhub/staff-scheduling-software)
| ![Icona note adesive](../media/o365-stickynotes-64x64.png) <br> [Sticky Notes](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Icona di Stream](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Icona Sway](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![icona di Teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) | ![Icona da fare](../media/o365-todo-64x64.png) <br> [Da fare](https://todo.microsoft.com) 
| ![Icona Visio](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Icona lavagna](../media/o365-whiteboard-64x64.png) <br> [Lavagna<sup>1</sup>,<sup>2</sup>](https://whiteboard.microsoft.com/) | ![Icona Word](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Icona di Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview) | ![Icona di Yammer](../media/o365-yammer-64x64.png) <br> [<br>Notificatore di Yammer](https://products.office.com/yammer/yammer-overview) |  |

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Icona di Azure](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Icona di Exchange](../media/o365-exchange-64x64.png) <br> [PowerShell di Exchange Online <br>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | ![Icona di SharePoint](../media/o365-sharepoint-64x64.png) <br> [PowerShell di SharePoint Online <br>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> supporto per lavagna e Skype for business su Web App disponibile a breve. <br>
> <sup>2</sup> supporto per lavagna su Android disponibile a breve.

## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
