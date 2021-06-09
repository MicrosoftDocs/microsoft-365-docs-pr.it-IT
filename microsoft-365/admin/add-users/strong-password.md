---
title: Disattivare i requisiti di password complessa per gli utenti
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come impostare requisiti di password complessa per gli utenti, usando Windows PowerShell.
ms.openlocfilehash: 898eaf30d813e883e88c3ccc8ff500d72ae72854
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840659"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Disattivare i requisiti di password complessa per gli utenti

In questo articolo viene illustrato come disattivare i requisiti di password complessa per gli utenti. I requisiti di password complessa sono attivati per impostazione predefinita nell'organizzazione Microsoft 365 per le aziende. L'organizzazione potrebbe avere requisiti per disabilitare password complesse. Seguire i passaggi seguenti per disattivare i requisiti di password complessa. È necessario completare questi passaggi con PowerShell.

## <a name="before-you-begin"></a>Prima di iniziare

Questo articolo è per gli utenti che gestiscono i criteri password per un'azienda, un istituto di istruzione o un'organizzazione no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account amministratore?](/microsoft-365/business-video/admin-center-overview) Per eseguire questa [procedura, è](about-admin-roles.md) necessario essere un amministratore globale o un amministratore delle password.

È inoltre necessario connettersi a Microsoft 365 con PowerShell.

## <a name="set-strong-passwords"></a>Impostare password complesse

1. [Connessione per Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Usando PowerShell, è possibile disattivare i requisiti di password complessa per tutti gli utenti con il comando seguente:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName deve essere nel formato di accesso in stile Internet in cui il nome utente è seguito dal simbolo di accesso (@) e da un nome di dominio. Ad esempio: user@contoso.com.

## <a name="related-content"></a>Contenuto correlato

[Come connettersi a Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Ulteriori informazioni sui comandi MsolUser di PowerShell](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Ulteriori informazioni sui criteri password](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)