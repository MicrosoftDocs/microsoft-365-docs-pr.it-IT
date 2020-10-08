---
title: Supporto delle app client Microsoft 365-accesso condizionale
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
description: In questo articolo vengono fornite informazioni sulle piattaforme, i client e i moduli di PowerShell che supportano l'accesso condizionale per Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d44dffd6da91be9e64953d1b744043114ba68183
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384920"
---
# <a name="microsoft-365-client-app-support--conditional-access"></a>Supporto delle app client Microsoft 365-accesso condizionale

Nei luoghi di lavoro moderni, gli utenti possono accedere alle risorse dell'organizzazione utilizzando vari dispositivi e app da qualsiasi luogo. Di conseguenza, solo concentrarsi su chi può accedere a una risorsa non è più sufficiente. L'organizzazione deve anche supportare la modalità e la posizione di accesso a una risorsa nell'infrastruttura di controllo di accesso.

Con il dispositivo di Azure Active Directory (Azure AD), il percorso e l'accesso condizionale basato sull'autenticazione a più fattori, è possibile rispondere a questo nuovo requisito. L'accesso condizionale è una funzionalità di Azure AD che consente di imporre controlli sull'accesso alle app nell'ambiente, in base a condizioni specifiche e gestiti da una posizione centrale.

Leggere altre informazioni sull'[Accesso condizionale di Azure AD](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-platforms"></a>Piattaforme supportate

 - Desktop di Windows 10
 - App di Windows 10 moderne
 - Web browser
 - Android
 - iOS
 - macOS<sup>1</sup>

Per ulteriori informazioni sul supporto delle piattaforme in Microsoft 365, vedere [requisiti di sistema per microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

## <a name="supported-clients"></a>Client supportati

Le versioni più recenti dei client seguenti supportano l'accesso condizionale:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Icona di Azure](../media/o365-azure-64x64.png) <br> [Portale di Azure AD <br>](https://azure.microsoft.com/features/azure-portal/) | ![Icona Access](../media/o365-access-64x64.png) <br> [Access](https://products.office.com/access) | ![Icona portale aziendale](../media/o365-microsoft-64x64.png) <br> [<br>Portale aziendale](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal)  | ![Icona Cortana](../media/o365-cortana-64x64.png) <br> [Cortana](https://www.microsoft.com/cortana) | ![Icona di approfondimento](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) 
| ![Icona Dynamics 365](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) | ![Icona del server perimetrale](../media/o365-edge-64x64.png) <br> [Edge](https://www.microsoft.com/windows/microsoft-edge) | ![Icona di Exchange](../media/o365-exchange-64x64.png) <br> [Exchange](https://products.office.com/exchange/exchange-online) | ![Icona Excel](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Icona maschere](../media/o365-forms-64x64.png) <br> [Maschere](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) 
| ![Icona di Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Icona Office.com](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Icona dell'obiettivo](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Icona di amministrazione di Office 365](../media/o365-o365admin-64x64.png) <br> [Microsoft 365 <br> amministratore](https://products.office.com/business/manage-office-365-admin-app) | ![Icona di OneDrive for business](../media/o365-OneDrive-64x64.png) <br> [OneDrive<sup>1</sup>](https://products.office.com/onedrive-for-business/online-cloud-storage) 
| ![Icona di OneNote](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Icona di Outlook](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) | ![Icona Planner](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![Icona di PowerApps](../media/o365-powerapps-64x64.png) <br> [PowerApps](https://powerapps.microsoft.com) | ![Icona Power automatizzate](../media/o365-flow-64x64.png) <br> [<br>Automatizzare la potenza](https://flow.microsoft.com)
| ![Icona PowerBI](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com) | ![Icona PowerPoint](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) | ![Icona progetto](../media/o365-project-64x64.png) <br> [Progetto](https://products.office.com/project) | ![Icona di Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![Icona di SharePoint](../media/o365-sharepoint-64x64.png) <br> [SharePoint](https://products.office.com/sharepoint) 
| ![Icona di Skype for Business](../media/o365-skypeforbusiness-64x64.png) <br> [Skype for <br> business](https://www.skype.com/business/) | ![Icona note adesive](../media/o365-stickynotes-64x64.png) <br> [Sticky Notes](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Icona di Stream](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Icona Sway](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![icona di Teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) 
| ![Icona da fare](../media/o365-todo-64x64.png) <br> [Da fare](https://todo.microsoft.com) | ![Icona Visio](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Icona Word](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Icona di Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview)

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Icona di Azure](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Icona di Exchange](../media/o365-exchange-64x64.png) <br> [PowerShell di Exchange Online <br>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![Icona di SharePoint](../media/o365-sharepoint-64x64.png) <br> [PowerShell di SharePoint Online <br>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> supporto per OneDrive su MacOS disponibile a breve.

## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
