---
title: Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: "Riepilogo: Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell."
ms.openlocfilehash: 18ff8e1789242b4dde3b4b31aaccf2462e4c5d74
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905129"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell

Quando si usa PowerShell per gestire Microsoft 365, è possibile aprire contemporaneamente più sessioni di PowerShell. Si potrebbero avere finestre di PowerShell diverse per gestire gli account utente, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e il Centro sicurezza &amp; conformità.
  
Non si tratta di uno scenario ottimale per la gestione di Microsoft 365, poiché non è possibile gestire i servizi scambiando i dati tra le finestre. Questo articolo descrive come usare una singola istanza di PowerShell per gestire gli account di Microsoft 365, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams e il Centro sicurezza &amp; conformità.

>[!Note]
>Questo articolo contiene al momento solo i comandi per connettersi al cloud internazionale (+GCC). Le note contengono collegamenti agli articoli con informazioni sulla connessione ad altri cloud di Microsoft 365.

## <a name="before-you-begin"></a>Prima di iniziare

Per poter gestire tutti i servizi di Microsoft 365 da una singola istanza di PowerShell, prendere in considerazione i prerequisiti seguenti:
  
- L'account aziendale o dell'istituto di istruzione di Microsoft 365 usato per queste procedure deve avere un ruolo di amministratore di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md). Questo è un requisito per PowerShell per Microsoft 365, ma non necessariamente per tutti gli altri servizi di Microsoft 365.
    
- È possibile usare le seguenti versioni a 64 bit di Windows:
    
  - Windows 10
    
  - Windows 8.1 o Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 o Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* È necessario installare Microsoft .NET Framework 4.5.*x* e quindi Windows Management Framework 3.0 o 4.0. Per altre informazioni, vedere [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).
    
    È necessario utilizzare una versione a 64 bit di Windows, a causa dei requisiti, per il modulo di Skype for Business Online e una per moduli di Microsoft 365.
    
- È necessario installare i moduli necessari per Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online e Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype for Business Online, moduli PowerShell](/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Panoramica di PowerShell per Teams](/microsoftteams/teams-powershell-overview)
    
-  PowerShell deve essere configurato per l'esecuzione di script firmati per Skype for Business Online e il Centro sicurezza &amp; conformità. Eseguire il comando seguente in una sessione di PowerShell con privilegi elevati, ossia una sessione di PowerShell aperta usando **Esegui come amministratore**.
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>Procedura di connessione se si usa solo una password

Seguire questa procedura per connettersi a tutti i servizi in una singola finestra di PowerShell se si usa solo una password per accedere.
  
1. Aprire Windows PowerShell.
    
2. Eseguire il comando seguente e immettere le credenziali dell'account aziendale o dell'Istituto di istruzione di Microsoft 365.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Eseguire questo comando per connettersi ad Azure AD tramite il modulo di Azure Active Directory PowerShell per Graph.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   In alternativa, se si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell, eseguire il comando seguente.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome. È necessario eseguire questi cmdlet da PowerShell.

4. Eseguire i comandi seguenti per la connessione a SharePoint Online. Specificare il nome dell'organizzazione per il dominio. Ad esempio, per "litwareinc\.onmicrosoft.com", il valore del nome dell'organizzazione è "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Eseguire questi comandi per connettersi a Skype for Business Online. La prima volta che ci si connette, verrà visualizzato un messaggio di avviso relativo all'aumento del valore `WSMan NetworkDelayms`. Ignorarlo.
     
   > [!Note]
   > Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente. Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online.
   
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

6. Eseguire i comandi seguenti per la connessione a Exchange Online.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > Per connettersi a Exchange Online per i cloud di Microsoft 365 diversi da quello internazionale, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

7. Eseguire i comandi seguenti per connettersi al Centro sicurezza &amp; conformità.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Per connettersi al Centro sicurezza &amp; conformità per i cloud di Microsoft 365 diversi da quello internazionale, vedere [Connettersi al Centro sicurezza e conformità di PowerShell](/powershell/exchange/connect-to-scc-powershell).

8. Eseguire i comandi seguenti per connettersi a PowerShell di Teams.
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Per connettersi a cloud di Microsoft Teams diversi da quello ** internazionale, vedere [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).
  



### <a name="azure-active-directory-powershell-for-graph-module"></a>Modulo di Azure Active Directory PowerShell per Graph

Di seguito sono elencati i comandi per tutti i servizi in un unico blocco quando si usa il modulo di Azure Active Directory PowerShell per Graph. Specificare il nome dell'host del dominio e l'UPN per l'accesso, quindi eseguirli tutti contemporaneamente.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Modulo di Microsoft Azure Active Directory per Windows PowerShell

Di seguito sono elencati i comandi per tutti i servizi in un unico blocco, quando si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell. Specificare il nome dell'host del dominio e l'UPN per l'accesso ed eseguirli tutti contemporaneamente.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Procedura di connessione quando si usa l'autenticazione a più fattori

### <a name="azure-active-directory-powershell-for-graph-module"></a>Modulo di Azure Active Directory PowerShell per Graph

Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 quando si usa l'autenticazione a più fattori con il modulo di Azure Active Directory PowerShell per Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Modulo di Microsoft Azure Active Directory per Windows PowerShell

Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 quando si usa l'autenticazione a più fattori con il Modulo di Microsoft Azure Active Directory per Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Chiudere la finestra di PowerShell

Per chiudere la finestra di PowerShell, eseguire questo comando per rimuovere le sessioni attive verso Skype for Business Online, SharePoint Online e Teams:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>Vedere anche

- [Collegarsi a Microsoft 365 con PowerShell](connect-to-microsoft-365-powershell.md)
- [Gestire SharePoint Online con PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)