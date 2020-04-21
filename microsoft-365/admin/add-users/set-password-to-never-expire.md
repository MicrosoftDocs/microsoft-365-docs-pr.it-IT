---
title: Impostare la password di un singolo utente in modo che non scada mai
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Informazioni su come impostare le singole password utente in modo che non scadano mai, utilizzando Windows PowerShell.
ms.openlocfilehash: 66c4901d171f5ed2e07d7a9f5cccbf141dc3d04d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43624035"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="4bc31-103">Impostare la password di un singolo utente in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="4bc31-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="4bc31-104">Impostare i criteri di scadenza delle password per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4bc31-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="4bc31-105">Nell'interfaccia di amministrazione passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">protezione & privacy</a> .</span><span class="sxs-lookup"><span data-stu-id="4bc31-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="4bc31-106">Accanto a **criteri password** selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="4bc31-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="4bc31-107">Se le password sono impostate su non scadono mai, impostare l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="4bc31-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="4bc31-108">Si otterrà l'opzione per specificare il numero di giorni fino alla scadenza delle password.</span><span class="sxs-lookup"><span data-stu-id="4bc31-108">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="4bc31-109">Impostare i criteri di scadenza delle password per i singoli utenti</span><span class="sxs-lookup"><span data-stu-id="4bc31-109">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="4bc31-110">Un amministratore globale per un servizio cloud di Microsoft può utilizzare [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) per impostare le password che non scadono per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4bc31-110">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="4bc31-111">È inoltre possibile utilizzare i cmdlet di [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) per rimuovere la configurazione senza scadenza o per vedere quali password utente sono impostate su Never expire.</span><span class="sxs-lookup"><span data-stu-id="4bc31-111">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="4bc31-112">Questa guida è applicabile ad altri provider, ad esempio Intune e Microsoft 365, che si basano anche su Azure AD per i servizi di identità e directory.</span><span class="sxs-lookup"><span data-stu-id="4bc31-112">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="4bc31-113">La scadenza della password è l'unica parte del criterio che può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="4bc31-113">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="4bc31-114">Per ulteriori informazioni su Azure AD PowerShell per Graph, vedere [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="4bc31-114">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="4bc31-115">Solo le password per gli account utente che non sono sincronizzati tramite la sincronizzazione della directory possono essere configurate in modo da non scadere.</span><span class="sxs-lookup"><span data-stu-id="4bc31-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="4bc31-116">Per ulteriori informazioni sulla sincronizzazione della directory, vedere [Connect ad con Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="4bc31-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="4bc31-117">Come controllare i criteri di scadenza per una password</span><span class="sxs-lookup"><span data-stu-id="4bc31-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="4bc31-118">Per ulteriori informazioni sul comando Get-AzureADUser nel modulo AzureAD, vedere l'articolo di riferimento [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="4bc31-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="4bc31-119">Eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bc31-119">Run one of the following commands:</span></span>

- <span data-ttu-id="4bc31-120">Per verificare se la password di un singolo utente è impostata su Never expire, eseguire il cmdlet seguente utilizzando l'UPN (ad esempio, *user@contoso.onmicrosoft.com*) o l'ID utente dell'utente che si desidera controllare:</span><span class="sxs-lookup"><span data-stu-id="4bc31-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="4bc31-121">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4bc31-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="4bc31-122">Per visualizzare l'impostazione Nessuna **scadenza password** per tutti gli utenti, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="4bc31-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="4bc31-123">Per ottenere un report di tutti gli utenti con PasswordNeverExpires in formato HTML sul desktop dell'utente corrente con nome **ReportPasswordNeverExpires. html**</span><span class="sxs-lookup"><span data-stu-id="4bc31-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="4bc31-124">Per ottenere un report di tutti gli utenti con PasswordNeverExpires in formato CSV sul desktop dell'utente corrente con nome **ReportPasswordNeverExpires. csv**</span><span class="sxs-lookup"><span data-stu-id="4bc31-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="4bc31-125">Impostare una password per la scadenza</span><span class="sxs-lookup"><span data-stu-id="4bc31-125">Set a password to expire</span></span>

<span data-ttu-id="4bc31-126">Eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bc31-126">Run one of the following commands:</span></span>

- <span data-ttu-id="4bc31-127">Per impostare la password di un utente in modo che la password scada, eseguire il cmdlet seguente utilizzando l'UPN o l'ID utente dell'utente:</span><span class="sxs-lookup"><span data-stu-id="4bc31-127">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="4bc31-128">Per impostare le password di tutti gli utenti dell'organizzazione in modo che scadano, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="4bc31-128">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="4bc31-129">Impostare una password in modo che non scada mai</span><span class="sxs-lookup"><span data-stu-id="4bc31-129">Set a password to never expire</span></span>

<span data-ttu-id="4bc31-130">Eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bc31-130">Run one of the following commands:</span></span>

- <span data-ttu-id="4bc31-131">Per impostare la password di un utente in modo che non scada mai, eseguire il cmdlet seguente utilizzando l'UPN o l'ID utente dell'utente:</span><span class="sxs-lookup"><span data-stu-id="4bc31-131">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="4bc31-132">Per impostare le password di tutti gli utenti di un'organizzazione per non scadere mai, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="4bc31-132">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="4bc31-133">Password impostate su `-PasswordPolicies DisablePasswordExpiration` still Age in base all' `pwdLastSet` attributo.</span><span class="sxs-lookup"><span data-stu-id="4bc31-133">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="4bc31-134">Se si impostano le password utente in modo che non scadano mai e quindi passano 90 giorni, le password scadono.</span><span class="sxs-lookup"><span data-stu-id="4bc31-134">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="4bc31-135">In base all' `pwdLastSet` attributo, se si modifica la scadenza `-PasswordPolicies None`, tutte le password con un `pwdLastSet` tempo precedente a 90 giorni richiedono all'utente di modificarle al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="4bc31-135">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="4bc31-136">Questa modifica può influire su un numero elevato di utenti.</span><span class="sxs-lookup"><span data-stu-id="4bc31-136">This change can affect a large number of users.</span></span>
