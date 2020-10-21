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
ms.openlocfilehash: 9f6fd61396d99245ffeabf757d3cb65c5d5cb85e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646620"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="5d130-103">Impostare il requisito di password complessa per gli utenti</span><span class="sxs-lookup"><span data-stu-id="5d130-103">Set strong password requirement for users</span></span>

<span data-ttu-id="5d130-104">In questo articolo viene illustrato come disattivare i requisiti di password complessa per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5d130-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="5d130-105">I requisiti per le password forti sono attivati per impostazione predefinita nell'organizzazione Microsoft 365 for business.</span><span class="sxs-lookup"><span data-stu-id="5d130-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="5d130-106">È possibile che l'organizzazione disponga di requisiti per disabilitare password complesse.</span><span class="sxs-lookup"><span data-stu-id="5d130-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="5d130-107">Seguire i passaggi descritti di seguito per disattivare i requisiti di password complessa.</span><span class="sxs-lookup"><span data-stu-id="5d130-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="5d130-108">Per eseguire questa procedura è necessario utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d130-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5d130-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="5d130-109">Before you begin</span></span>

<span data-ttu-id="5d130-110">Questo articolo è destinato agli utenti che gestiscono i criteri di password per un'azienda, una scuola o un no profit.</span><span class="sxs-lookup"><span data-stu-id="5d130-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="5d130-111">Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5d130-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="5d130-112">Che cos'è un account di amministratore?</span><span class="sxs-lookup"><span data-stu-id="5d130-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="5d130-113">Per eseguire questa procedura è necessario essere un [amministratore globale o una password](about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="5d130-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="5d130-114">È inoltre necessario connettersi a Microsoft 365 con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d130-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="5d130-115">Impostare password complesse</span><span class="sxs-lookup"><span data-stu-id="5d130-115">Set strong passwords</span></span>

1. <span data-ttu-id="5d130-116">[Connettersi a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5d130-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="5d130-117">Tramite PowerShell, è possibile disattivare i requisiti di password complessa per tutti gli utenti con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5d130-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="5d130-118">Il userPrincipalName deve trovarsi nel formato di accesso di tipo Internet, in cui il nome utente è seguito dal segno di chiocciola (@) e da un nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="5d130-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="5d130-119">Ad esempio: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5d130-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="5d130-120">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="5d130-120">Related content</span></span>

[<span data-ttu-id="5d130-121">Come connettersi a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d130-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="5d130-122">Ulteriori informazioni sui comandi di MsolUser di PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d130-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="5d130-123">Ulteriori informazioni sui criteri password</span><span class="sxs-lookup"><span data-stu-id="5d130-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)