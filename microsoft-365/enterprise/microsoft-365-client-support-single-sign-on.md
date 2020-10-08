---
title: Supporto delle app client Microsoft 365-Single Sign-on
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
ms.openlocfilehash: d0a45c30ffe736cf67e811bce6eb029d6fb50674
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384807"
---
# <a name="microsoft-365-client-app-support--single-sign-on"></a>Supporto delle app client Microsoft 365-Single Sign-on

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Single Sign-on (SSO) aggiunge la sicurezza e la convenienza quando gli utenti eseguono l'accesso alle applicazioni in Azure Active Directory (Azure AD). Con Single Sign-on, gli utenti accedono una volta con un account per accedere ai dispositivi di servizi di dominio Active Directory (AD DS), software as a Service (SaaS) e applicazioni Web locali.

Per ulteriori informazioni, vedere [Single Sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="supported-platforms"></a>Piattaforme supportate

 - Windows 10 Desktop<sup>2</sup>
 - App di Windows 10 moderne
 - Web browser
 - Android<sup>3</sup>
 - iOS<sup>1</sup>
 - macOS<sup>4</sup>

Per ulteriori informazioni sul supporto delle piattaforme in Microsoft 365, vedere [requisiti di sistema per microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

## <a name="supported-clients"></a>Client supportati

Le versioni più recenti dei client seguenti supportano il servizio Single Sign-on:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Icona Access](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Icona portale aziendale](../media/o365-microsoft-64x64.png) <br> [<br>Portale aziendale<sup>3, 4</sup>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | ![Icona di approfondimento](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) | ![Icona del server perimetrale](../media/o365-edge-64x64.png) <br> [Edge<sup>1</sup>](https://www.microsoft.com/windows/microsoft-edge) | ![Icona Excel](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) 
| ![Icona di Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala<sup>1</sup>](https://products.office.com/en/business/microsoft-kaizala) | ![Icona Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Icona dell'obiettivo](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Icona di OneDrive for business](../media/o365-OneDrive-64x64.png) <br> [OneDrive](https://products.office.com/onedrive-for-business/online-cloud-storage) | ![Icona di OneNote](../media/o365-OneNote-64x64.png) <br> [OneNote<sup>2</sup>](https://products.office.com/onenote) 
| ![Icona di Outlook](../media/o365-outlook-64x64.png) <br> [Outlook<sup>4</sup>](https://products.office.com/outlook) | ![Icona Planner](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Icona Power automatizzate](../media/o365-flow-64x64.png) <br> [<br>Automatizzare la potenza](https://flow.microsoft.com) | ![Icona PowerBI](../media/o365-powerbi-64x64.png) <br> [Alimentazione BI<sup>2</sup>](https://powerbi.microsoft.com)| ![Icona PowerPoint](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) 
| ![Icona progetto](../media/o365-project-64x64.png) <br> [Progetto](https://products.office.com/project) | ![Icona di Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![Icona di SharePoint](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) | ![Icona note adesive](../media/o365-stickynotes-64x64.png) <br> [Sticky Notes](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw)  | ![Icona Sway](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) 
| ![icona di Teams](../media/o365-teams-64x64.png) <br> [Teams<sup>2, 4</sup>](https://products.office.com/microsoft-teams/group-chat-software) | ![Icona da fare](../media/o365-todo-64x64.png) <br> [Da fare](https://todo.microsoft.com) | ![Icona Visio](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Icona lavagna](../media/o365-whiteboard-64x64.png) <br> [Lavagna<sup>3</sup>](https://whiteboard.microsoft.com/) | ![Icona Word](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) 
| ![Icona di Yammer](../media/o365-yammer-64x64.png) <br> [Yammer<sup>2</sup>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Icona di Azure](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Icona di Exchange](../media/o365-exchange-64x64.png) <br> [PowerShell di Exchange Online <br>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![Icona di SharePoint](../media/o365-sharepoint-64x64.png) <br> [PowerShell di SharePoint Online <br>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> supporto per Edge e Kaizala su iOS disponibile a breve. <br>
> <sup>2</sup> supporto per OneNote, PowerBI, teams e Yammer sul desktop di Windows 10 disponibile a breve. <br>
> <sup>3</sup> supporto per lavagna su Android disponibile a breve. <br>
> <sup>4</sup> supporto per Outlook, teams e il portale aziendale su MacOS disponibile a breve. <br>

## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
