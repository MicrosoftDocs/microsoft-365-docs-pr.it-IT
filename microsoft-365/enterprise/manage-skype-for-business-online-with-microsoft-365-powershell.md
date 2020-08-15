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
description: 'Sintesi: Utilizzare PowerShell per Microsoft 365 per gestire i criteri, i criteri per gli utenti e le impostazioni delle riunioni di Skype for Business online.'
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691407"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Gestire Skype for Business Online con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Una delle attività principali di qualsiasi amministratore di Skype for Business Online è la gestione dei criteri. Anche se è possibile eseguire alcune di queste operazioni nell'interfaccia di amministrazione di Microsoft 365, altre attività sono molto più rapide e semplici in PowerShell. 

## <a name="before-you-start"></a>Prima di iniziare

Scaricare e installare il [Modulo di Windows PowerShell per Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366), quindi riavviare il computer.


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a>Accedere usando il nome utente e la password di un account amministratore di Skype for Business Online

1. Aprire il prompt dei comandi Windows PowerShell ed eseguire quanto segue: 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, scrivere nome utente e password dell'account amministratore di Skype for Business, e quindi fare clic su **OK**.


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a>Accedere con un account amministratore di Skype for Business Online usando l'autenticazione a più fattori

1. Aprire il prompt dei comandi Windows PowerShell ed eseguire quanto segue:

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. Quando richiesto dal comando **New-CsOnlineSession**, immettere il nome dell'account amministratore di Skype for Business Online.

3. Nella finestra di dialogo **Accedi al tuo account**, scrivere la password dell'account amministratore di Skype for Business Online e cliccare su **Accedi**.

4. Seguire le istruzioni della finestra di dialogo **Accedi al tuo account** per fornire informazioni di autenticazione aggiuntive, come un codice di verifica, quindi fare clic su **Verifica**.

Per ulteriori informazioni, vedere i seguenti argomenti:
  
- [Gestire i criteri di Skype for Business Online con PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Assegnare i criteri di Skype for Business Online con PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Vedere anche

[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Riferimenti per i cmdlet di PowerShell per Skype for Business](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

