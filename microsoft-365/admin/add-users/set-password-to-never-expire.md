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
description: Informazioni su come impostare le singole password utente in modo che non scadano mai, utilizzando Windows PowerShell.
ms.openlocfilehash: 2d60a8312be070d3f56cfef7cfb93e6c5da32991
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580638"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Impostare la password di un singolo utente in modo che non scada mai

In questo articolo viene illustrato come impostare una password per un singolo utente in modo che non scada. Per eseguire questa procedura è necessario utilizzare PowerShell.

## <a name="before-you-begin"></a>Prima di iniziare

Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account amministratore?](../admin-overview/admin-overview.md). 

Per eseguire questa procedura è necessario essere un [amministratore globale o una password](about-admin-roles.md) .

Un amministratore globale per un servizio cloud di Microsoft può utilizzare [Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) per impostare le password che non scadono per utenti specifici. È inoltre possibile utilizzare i cmdlet di [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) per rimuovere la configurazione senza scadenza o per vedere quali password utente sono impostate su Never expire.

Questa guida è applicabile ad altri provider, ad esempio Intune e Microsoft 365, che si basano anche su Azure AD per i servizi di identità e directory. La scadenza della password è l'unica parte del criterio che può essere modificata.

> [!NOTE]
> Solo le password per gli account utente che non sono sincronizzati tramite la sincronizzazione della directory possono essere configurate in modo da non scadere. Per ulteriori informazioni sulla sincronizzazione della directory, vedere [Connect ad con Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Come controllare i criteri di scadenza per una password

Per ulteriori informazioni sul comando Get-AzureADUser nel modulo AzureAD, vedere l'articolo di riferimento [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Eseguire uno dei comandi riportati di seguito:

- Per verificare se la password di un singolo utente è impostata su Never expire, eseguire il cmdlet seguente utilizzando l'UPN (ad esempio, *user@contoso.onmicrosoft.com*) o l'ID utente dell'utente che si desidera controllare:

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    Esempio:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- Per visualizzare l'impostazione Nessuna **scadenza password** per tutti gli utenti, eseguire il cmdlet seguente:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Per ottenere un report di tutti gli utenti con PasswordNeverExpires in formato HTML sul desktop dell'utente corrente con nome  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Per ottenere un report di tutti gli utenti con PasswordNeverExpires in formato CSV sul desktop dell'utente corrente con nome **ReportPasswordNeverExpires.csv**

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

- Per impostare le password di tutti gli utenti di un'organizzazione per non scadere mai, eseguire il cmdlet seguente:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Gli account utente configurati con il `-PasswordPolicies DisablePasswordExpiration` parametro Age è ancora basato sull' `pwdLastSet` attributo. In base all' `pwdLastSet` attributo, se si modifica la data di scadenza `-PasswordPolicies None` , tutte le password con un pwdLastSet precedente a 90 giorni richiedono all'utente di modificarle al successivo accesso. Questa modifica può influire su un numero elevato di utenti.

### <a name="set-a-password-to-expire"></a>Impostare una password per la scadenza

Eseguire uno dei comandi riportati di seguito:

- Per impostare la password di un utente in modo che la password scada, eseguire il cmdlet seguente utilizzando l'UPN o l'ID utente dell'utente:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Per impostare le password di tutti gli utenti dell'organizzazione in modo che scadano, utilizzare il cmdlet seguente:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Contenuti correlati

[Consentire agli utenti di reimpostare le loro password](../add-users/let-users-reset-passwords.md)

[Reimpostare password](../add-users/reset-passwords.md)