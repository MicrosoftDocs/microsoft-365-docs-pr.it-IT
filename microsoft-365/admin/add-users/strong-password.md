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
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="c1315-103">Impostare il requisito di password complessa per gli utenti</span><span class="sxs-lookup"><span data-stu-id="c1315-103">Set strong password requirement for users</span></span>

<span data-ttu-id="c1315-104">In questo articolo viene illustrato come impostare i requisiti di password complesse per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c1315-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="c1315-105">Per eseguire questa procedura è necessario utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1315-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c1315-106">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="c1315-106">Before you begin</span></span>

<span data-ttu-id="c1315-107">Questo articolo è destinato agli utenti che gestiscono i criteri di password per un'azienda, una scuola o un no profit.</span><span class="sxs-lookup"><span data-stu-id="c1315-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="c1315-108">Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1315-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="c1315-109">[Che cos'è un account amministratore?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c1315-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="c1315-110">Per eseguire questa procedura è necessario essere un [amministratore globale o una password](about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="c1315-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="c1315-111">È inoltre necessario connettersi a Microsoft 365 con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1315-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="c1315-112">Impostare password complesse</span><span class="sxs-lookup"><span data-stu-id="c1315-112">Set strong passwords</span></span>

1. <span data-ttu-id="c1315-113">[Connettersi a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="c1315-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="c1315-114">Tramite PowerShell, è possibile abilitare i requisiti di password complessa per tutti gli utenti con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c1315-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="c1315-115">Il userPrincipalName deve trovarsi nel formato di accesso di tipo Internet, in cui il nome utente è seguito dal segno di chiocciola (@) e da un nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="c1315-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="c1315-116">Ad esempio: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c1315-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="c1315-117">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="c1315-117">Related content</span></span>

[<span data-ttu-id="c1315-118">Come connettersi a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1315-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="c1315-119">Ulteriori informazioni sui comandi di MsolUser di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1315-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="c1315-120">Ulteriori informazioni sui criteri password</span><span class="sxs-lookup"><span data-stu-id="c1315-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)