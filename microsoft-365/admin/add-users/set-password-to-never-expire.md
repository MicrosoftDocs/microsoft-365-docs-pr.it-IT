---
title: Impostare la password di un singolo utente in modo che non scada mai
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
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Accedi al tuo account Microsoft 365 amministratore per impostare alcune password utente individuali in modo che non scada mai usando Windows PowerShell.
ms.openlocfilehash: 12c717d8d625b0135f185b1af131db00e9762c73
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635559"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="7dfb9-103">Impostare la password di un singolo utente in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="7dfb9-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="7dfb9-104">In questo articolo viene illustrato come impostare una password per un singolo utente in modo che non scada.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="7dfb9-105">È necessario completare questi passaggi con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7dfb9-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7dfb9-106">Before you begin</span></span>

<span data-ttu-id="7dfb9-107">Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="7dfb9-108">Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="7dfb9-109">[Che cos'è un account amministratore?](../../business-video/admin-center-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7dfb9-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="7dfb9-110">Per eseguire questa [procedura, è](about-admin-roles.md) necessario essere un amministratore globale o un amministratore delle password.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="7dfb9-111">Un amministratore globale di un servizio cloud Microsoft può usare Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) per Graph per impostare password che non scadono per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="7dfb9-112">È inoltre possibile utilizzare i cmdlet [di AzureAD](/powershell/module/Azuread) per rimuovere la configurazione senza scadenza o per vedere quali password utente sono impostate per non scadere mai.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="7dfb9-113">Questa guida si applica ad altri provider, ad esempio Intune e Microsoft 365, che si basano anche su Azure AD per i servizi di identità e directory.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="7dfb9-114">La scadenza della password è l'unica parte del criterio che può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="7dfb9-115">Solo le password per gli account utente non sincronizzati tramite la sincronizzazione della directory possono essere configurate in modo da non scadere.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="7dfb9-116">Per ulteriori informazioni sulla sincronizzazione della directory, [vedere Connessione AD con Azure AD.](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="7dfb9-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="7dfb9-117">Come controllare i criteri di scadenza per una password</span><span class="sxs-lookup"><span data-stu-id="7dfb9-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="7dfb9-118">Per ulteriori informazioni sul comando Get-AzureADUser nel modulo AzureAD, vedere l'articolo di riferimento [Get-AzureADUser.](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="7dfb9-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="7dfb9-119">Eseguire uno dei comandi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="7dfb9-119">Run one of the following commands:</span></span>

- <span data-ttu-id="7dfb9-120">Per verificare se la password di un singolo utente è impostata in modo che non scada mai, eseguire il cmdlet seguente utilizzando l'UPN (ad *esempio, user@contoso.onmicrosoft.com*) o l'ID utente dell'utente che si desidera controllare:</span><span class="sxs-lookup"><span data-stu-id="7dfb9-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="7dfb9-121">Esempio:</span><span class="sxs-lookup"><span data-stu-id="7dfb9-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="7dfb9-122">Per visualizzare **l'impostazione Nessuna scadenza** password per tutti gli utenti, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7dfb9-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="7dfb9-123">Per ottenere un report di tutti gli utenti con PasswordNeverExpires in Html sul desktop dell'utente corrente con nome  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="7dfb9-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="7dfb9-124">Per ottenere un report di tutti gli utenti con PasswordNeverExpires in CSV sul desktop dell'utente corrente con nome **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="7dfb9-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="7dfb9-125">Per impostare le password di tutti gli utenti di un'organizzazione in modo che non scada mai, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7dfb9-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="7dfb9-126">Gli account utente configurati con `-PasswordPolicies DisablePasswordExpiration` il parametro hanno ancora validità in base all'attributo. `pwdLastSet`</span><span class="sxs-lookup"><span data-stu-id="7dfb9-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="7dfb9-127">In base all'attributo, se si modifica la scadenza in , tutte le password con `pwdLastSet` `-PasswordPolicies None` pwdLastSet precedenti a 90 giorni richiedono all'utente di modificarle al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="7dfb9-128">Questa modifica può influire su un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="7dfb9-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="7dfb9-129">Impostare una password in modo che scada</span><span class="sxs-lookup"><span data-stu-id="7dfb9-129">Set a password to expire</span></span>

<span data-ttu-id="7dfb9-130">Eseguire uno dei comandi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="7dfb9-130">Run one of the following commands:</span></span>

- <span data-ttu-id="7dfb9-131">Per impostare la password di un utente in modo che scada, eseguire il cmdlet seguente utilizzando l'UPN o l'ID utente dell'utente:</span><span class="sxs-lookup"><span data-stu-id="7dfb9-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="7dfb9-132">Per impostare le password di tutti gli utenti dell'organizzazione in modo che scadano, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7dfb9-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="7dfb9-133">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="7dfb9-133">Related content</span></span>

<span data-ttu-id="7dfb9-134">[Consentire agli utenti di reimpostare le proprie password](../add-users/let-users-reset-passwords.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="7dfb9-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="7dfb9-135">[Reimpostare le password](../add-users/reset-passwords.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="7dfb9-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="7dfb9-136">[Impostare i criteri di scadenza delle password per l'organizzazione](../manage/set-password-expiration-policy.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="7dfb9-136">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>