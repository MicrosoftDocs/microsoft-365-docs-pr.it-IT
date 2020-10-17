---
title: Gestire Skype for Business Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Usare PowerShell per Microsoft 365 per gestire i criteri, i criteri per gli utenti e le impostazioni delle riunioni di Skype for Business online.
ms.openlocfilehash: ff35463dc0c2e16106432c393b10e31e6bf0a5d2
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477102"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Gestire Skype for Business Online con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Gli amministratori di Skype fo Business online sono responsabili della gestione dei criteri. Anche se è possibile eseguire alcune di queste operazioni nell'interfaccia di amministrazione di Microsoft 365, altre sono più facili da eseguire in PowerShell.

## <a name="before-you-start"></a>Prima di iniziare

  > [!Note]
   > Il connettore di Skype for Business Online fa parte al momento del modulo di Teams PowerShell più recente. Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online.
   
Installare il [modulo di PowerShell di Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).


## <a name="connect-using-admin-credentials"></a>Connettersi con le credenziali di amministratore.

1. Aprire la finestra del prompt dei comandi di Windows PowerShell ed eseguire i comandi seguenti:
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, digitare il nome utente e password dell'account amministratore, poi selezionare **OK**.


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Connettersi con un account di amministratore con l'autenticazione a più fattori

1. Aprire la finestra del prompt dei comandi di Windows PowerShell ed eseguire i seguenti comandi:

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. Quando richiesto dal comando **New-CsOnlineSession**, immettere il nome dell'account amministratore di Skype for Business Online.

3. Nella finestra di dialogo **Accedi al tuo account**, scrivere la password dell'account amministratore di Skype for Business Online e selezionare **Accedi**.

4. Nella finestra di dialogo **Accedi al tuo account** seguire le istruzioni per fornire informazioni di autenticazione aggiuntive, come un codice di verifica, quindi selezionare **Verifica**.

Per ulteriori informazioni, vedere:
  
- [Gestire i criteri di Skype for Business Online con PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Assegnare i criteri di Skype for Business Online con PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Vedere anche

[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Riferimenti per i cmdlet di PowerShell per Skype for Business](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
