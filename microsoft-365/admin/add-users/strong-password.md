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
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="baf3c-103">Disattivare i requisiti di password complessa per gli utenti</span><span class="sxs-lookup"><span data-stu-id="baf3c-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="baf3c-104">In questo articolo viene illustrato come disattivare i requisiti di password complessa per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="baf3c-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="baf3c-105">I requisiti di password complessa sono attivati per impostazione predefinita nell'organizzazione Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="baf3c-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="baf3c-106">L'organizzazione potrebbe avere requisiti per disabilitare password complesse.</span><span class="sxs-lookup"><span data-stu-id="baf3c-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="baf3c-107">Seguire i passaggi seguenti per disattivare i requisiti di password complessa.</span><span class="sxs-lookup"><span data-stu-id="baf3c-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="baf3c-108">È necessario completare questi passaggi con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="baf3c-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="baf3c-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="baf3c-109">Before you begin</span></span>

<span data-ttu-id="baf3c-110">Questo articolo è per gli utenti che gestiscono i criteri password per un'azienda, un istituto di istruzione o un'organizzazione no profit.</span><span class="sxs-lookup"><span data-stu-id="baf3c-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="baf3c-111">Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="baf3c-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="baf3c-112">Che cos'è un account amministratore?</span><span class="sxs-lookup"><span data-stu-id="baf3c-112">What's an admin account?</span></span>](/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="baf3c-113">Per eseguire questa [procedura, è](about-admin-roles.md) necessario essere un amministratore globale o un amministratore delle password.</span><span class="sxs-lookup"><span data-stu-id="baf3c-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="baf3c-114">È inoltre necessario connettersi a Microsoft 365 con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="baf3c-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="baf3c-115">Impostare password complesse</span><span class="sxs-lookup"><span data-stu-id="baf3c-115">Set strong passwords</span></span>

1. <span data-ttu-id="baf3c-116">[Connessione per Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="baf3c-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="baf3c-117">Usando PowerShell, è possibile disattivare i requisiti di password complessa per tutti gli utenti con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="baf3c-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="baf3c-118">UserPrincipalName deve essere nel formato di accesso in stile Internet in cui il nome utente è seguito dal simbolo di accesso (@) e da un nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="baf3c-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="baf3c-119">Ad esempio: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="baf3c-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="baf3c-120">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="baf3c-120">Related content</span></span>

[<span data-ttu-id="baf3c-121">Come connettersi a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="baf3c-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="baf3c-122">Ulteriori informazioni sui comandi MsolUser di PowerShell</span><span class="sxs-lookup"><span data-stu-id="baf3c-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="baf3c-123">Ulteriori informazioni sui criteri password</span><span class="sxs-lookup"><span data-stu-id="baf3c-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)