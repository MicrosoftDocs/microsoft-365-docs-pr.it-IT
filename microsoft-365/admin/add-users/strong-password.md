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
description: Informazioni su come impostare i requisiti di password complessa per gli utenti, utilizzando Windows PowerShell.
ms.openlocfilehash: f9a0b76d024cc18552657144e4ccf8de8a72f0d9
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655736"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Disattivare i requisiti di password complessa per gli utenti

In questo articolo viene illustrato come disattivare i requisiti di password complessa per gli utenti. I requisiti per le password forti sono attivati per impostazione predefinita nell'organizzazione Microsoft 365 for business. È possibile che l'organizzazione disponga di requisiti per disabilitare password complesse. Seguire i passaggi descritti di seguito per disattivare i requisiti di password complessa. Per eseguire questa procedura è necessario utilizzare PowerShell.

## <a name="before-you-begin"></a>Informazioni preliminari

Questo articolo è destinato agli utenti che gestiscono i criteri di password per un'azienda, una scuola o un no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account di amministratore?](../admin-overview/admin-overview.md) Per eseguire questa procedura è necessario essere un [amministratore globale o una password](about-admin-roles.md) .

È inoltre necessario connettersi a Microsoft 365 con PowerShell.

## <a name="set-strong-passwords"></a>Impostare password complesse

1. [Connettersi a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Tramite PowerShell, è possibile disattivare i requisiti di password complessa per tutti gli utenti con il comando seguente:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> Il userPrincipalName deve trovarsi nel formato di accesso di tipo Internet, in cui il nome utente è seguito dal segno di chiocciola (@) e da un nome di dominio. Ad esempio: user@contoso.com.

## <a name="related-content"></a>Contenuti correlati

[Come connettersi a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Ulteriori informazioni sui comandi di MsolUser di PowerShell](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Ulteriori informazioni sui criteri password](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)