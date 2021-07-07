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
ms.openlocfilehash: c9f0c245aca0e028183c42f6a257068d74aa563d
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326724"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Impostare la password di un singolo utente in modo che non scada mai

In questo articolo viene illustrato come impostare una password per un singolo utente in modo che non scada. È necessario completare questi passaggi con PowerShell.

## <a name="before-you-begin"></a>Prima di iniziare

Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account amministratore?](../../business-video/admin-center-overview.md).

Per eseguire questa [procedura, è](about-admin-roles.md) necessario essere un amministratore globale o un amministratore delle password.

Un amministratore globale di un servizio cloud Microsoft può usare Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2) per Graph per impostare password che non scadono per utenti specifici. È inoltre possibile utilizzare i cmdlet [di AzureAD](/powershell/module/Azuread) per rimuovere la configurazione senza scadenza o per vedere quali password utente sono impostate per non scadere mai.

Questa guida si applica ad altri provider, ad esempio Intune e Microsoft 365, che si basano anche su Azure AD per i servizi di identità e directory. La scadenza della password è l'unica parte del criterio che può essere modificata.


## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Come controllare i criteri di scadenza per una password

Per ulteriori informazioni sul comando Get-AzureADUser nel modulo AzureAD, vedere l'articolo di riferimento [Get-AzureADUser.](/powershell/module/Azuread/Get-AzureADUser)

Eseguire uno dei comandi riportati di seguito:

- Per verificare se la password di un singolo utente è impostata in modo che non scada mai, eseguire il cmdlet seguente utilizzando l'UPN (ad *esempio, user@contoso.onmicrosoft.com*) o l'ID utente dell'utente che si desidera controllare:

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

- Per visualizzare **l'impostazione Nessuna scadenza** password per tutti gli utenti, eseguire il cmdlet seguente:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Per ottenere un report di tutti gli utenti con PasswordNeverExpires in Html sul desktop dell'utente corrente con nome  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- Per ottenere un report di tutti gli utenti con PasswordNeverExpires in CSV sul desktop dell'utente corrente con nome **ReportPasswordNeverExpires.csv**

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

- Per impostare le password di tutti gli utenti di un'organizzazione in modo che non scada mai, eseguire il cmdlet seguente:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Gli account utente configurati con `-PasswordPolicies DisablePasswordExpiration` il parametro hanno ancora validità in base all'attributo. `pwdLastSet` In base all'attributo, se si modifica la scadenza in , tutte le password con `pwdLastSet` `-PasswordPolicies None` pwdLastSet precedenti a 90 giorni richiedono all'utente di modificarle al successivo accesso. Questa modifica può influire su un numero elevato di utenti.

### <a name="set-a-password-to-expire"></a>Impostare una password in modo che scada

Eseguire uno dei comandi riportati di seguito:

- Per impostare la password di un utente in modo che scada, eseguire il cmdlet seguente utilizzando l'UPN o l'ID utente dell'utente:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Per impostare le password di tutti gli utenti dell'organizzazione in modo che scadano, utilizzare il cmdlet seguente:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Contenuti correlati

[Consentire agli utenti di reimpostare le loro password](../add-users/let-users-reset-passwords.md) (articolo)\
[Reimpostare la password](../add-users/reset-passwords.md) (articolo)\
[Impostare i criteri di scadenza delle password per l'organizzazione](../manage/set-password-expiration-policy.md) (articolo)
