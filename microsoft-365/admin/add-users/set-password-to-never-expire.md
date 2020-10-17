---
title: Impostare la password di un singolo utente in modo che non scada mai
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: mnirkhe
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
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Informazioni su come impostare le singole password utente in modo che non scadano mai, utilizzando Windows PowerShell.
ms.openlocfilehash: e778ad8a020a6767934d51f8bc227bfc39b13a9b
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580917"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="8678c-103">Impostare la password di un singolo utente in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="8678c-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="8678c-104">In questo articolo viene illustrato come impostare una password per un singolo utente in modo che non scada.</span><span class="sxs-lookup"><span data-stu-id="8678c-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="8678c-105">Per eseguire questa procedura è necessario utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8678c-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8678c-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8678c-106">Before you begin</span></span>

<span data-ttu-id="8678c-107">Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit.</span><span class="sxs-lookup"><span data-stu-id="8678c-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="8678c-108">Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8678c-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="8678c-109">[Che cos'è un account amministratore?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8678c-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="8678c-110">Per eseguire questa procedura è necessario essere un [amministratore globale o una password](about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="8678c-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="8678c-111">Un amministratore globale per un servizio cloud di Microsoft può utilizzare [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) per impostare le password che non scadono per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="8678c-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="8678c-112">È inoltre possibile utilizzare i cmdlet di [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) per rimuovere la configurazione senza scadenza o per vedere quali password utente sono impostate su Never expire.</span><span class="sxs-lookup"><span data-stu-id="8678c-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="8678c-113">Questa guida è applicabile ad altri provider, ad esempio Intune e Microsoft 365, che si basano anche su Azure AD per i servizi di identità e directory.</span><span class="sxs-lookup"><span data-stu-id="8678c-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="8678c-114">La scadenza della password è l'unica parte del criterio che può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="8678c-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="8678c-115">Solo le password per gli account utente che non sono sincronizzati tramite la sincronizzazione della directory possono essere configurate in modo da non scadere.</span><span class="sxs-lookup"><span data-stu-id="8678c-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="8678c-116">Per ulteriori informazioni sulla sincronizzazione della directory, vedere [Connect ad con Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="8678c-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="8678c-117">Come controllare i criteri di scadenza per una password</span><span class="sxs-lookup"><span data-stu-id="8678c-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="8678c-118">Per ulteriori informazioni sul comando Get-AzureADUser nel modulo AzureAD, vedere l'articolo di riferimento [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="8678c-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="8678c-119">Eseguire uno dei comandi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="8678c-119">Run one of the following commands:</span></span>

- <span data-ttu-id="8678c-120">Per verificare se la password di un singolo utente è impostata su Never expire, eseguire il cmdlet seguente utilizzando l'UPN (ad esempio, *user@contoso.onmicrosoft.com*) o l'ID utente dell'utente che si desidera controllare:</span><span class="sxs-lookup"><span data-stu-id="8678c-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="8678c-121">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8678c-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="8678c-122">Per visualizzare l'impostazione Nessuna **scadenza password** per tutti gli utenti, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8678c-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="8678c-123">Per ottenere un report di tutti gli utenti con PasswordNeverExpires in formato HTML sul desktop dell'utente corrente con nome  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="8678c-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="8678c-124">Per ottenere un report di tutti gli utenti con PasswordNeverExpires in formato CSV sul desktop dell'utente corrente con nome **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="8678c-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="8678c-125">Per impostare le password di tutti gli utenti di un'organizzazione per non scadere mai, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8678c-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="8678c-126">Impostare una password per la scadenza</span><span class="sxs-lookup"><span data-stu-id="8678c-126">Set a password to expire</span></span>

<span data-ttu-id="8678c-127">Eseguire uno dei comandi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="8678c-127">Run one of the following commands:</span></span>

- <span data-ttu-id="8678c-128">Per impostare la password di un utente in modo che la password scada, eseguire il cmdlet seguente utilizzando l'UPN o l'ID utente dell'utente:</span><span class="sxs-lookup"><span data-stu-id="8678c-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="8678c-129">Per impostare le password di tutti gli utenti dell'organizzazione in modo che scadano, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8678c-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="8678c-130">Account utente configurati con il `-PasswordPolicies DisablePasswordExpiration` parametro still Age in base all' `pwdLastSet` attributo dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="8678c-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="8678c-131">Ad esempio, se si impostano le password degli utenti a non scadere mai e quindi 90 o più giorni passano, le password scadono ancora.</span><span class="sxs-lookup"><span data-stu-id="8678c-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="8678c-132">In base all' `pwdLastSet` attributo dell'account utente, per gli account utente configurati con il `-PasswordPolicies None` parametro, tutte le password con un `pwdLastSet` tempo precedente a 90 giorni richiedono all'utente di modificarle al successivo accesso. Questa modifica può influire su un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="8678c-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="8678c-133">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="8678c-133">Related content</span></span>

[<span data-ttu-id="8678c-134">Consentire agli utenti di reimpostare le loro password</span><span class="sxs-lookup"><span data-stu-id="8678c-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="8678c-135">Reimpostare password</span><span class="sxs-lookup"><span data-stu-id="8678c-135">Reset passwords</span></span>](../add-users/reset-passwords.md)