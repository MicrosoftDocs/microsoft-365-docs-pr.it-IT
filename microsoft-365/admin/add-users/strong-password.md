---
title: Impostare il requisito di password complessa per gli utenti
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
description: Informazioni su come impostare i requisiti di password complessa per gli utenti, utilizzando Windows PowerShell.
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626144"
---
# <a name="set-strong-password-requirement-for-users"></a>Impostare il requisito di password complessa per gli utenti

In questo articolo viene illustrato come impostare i requisiti di password complesse per gli utenti. Per eseguire questa procedura è necessario utilizzare PowerShell.

## <a name="before-you-begin"></a>Informazioni preliminari

Questo articolo è destinato agli utenti che gestiscono i criteri di password per un'azienda, una scuola o un no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account amministratore?](../admin-overview/admin-overview.md). Per eseguire questa procedura è necessario essere un [amministratore globale o una password](about-admin-roles.md) .

È inoltre necessario connettersi a Microsoft 365 con PowerShell.

## <a name="set-strong-passwords"></a>Impostare password complesse

1. [Connettersi a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Tramite PowerShell, è possibile abilitare i requisiti di password complessa per tutti gli utenti con il comando seguente:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> Il userPrincipalName deve trovarsi nel formato di accesso di tipo Internet, in cui il nome utente è seguito dal segno di chiocciola (@) e da un nome di dominio. Ad esempio: user@contoso.com.

## <a name="related-content"></a>Contenuti correlati

[Come connettersi a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Ulteriori informazioni sui comandi di MsolUser di PowerShell](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Ulteriori informazioni sui criteri password](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)