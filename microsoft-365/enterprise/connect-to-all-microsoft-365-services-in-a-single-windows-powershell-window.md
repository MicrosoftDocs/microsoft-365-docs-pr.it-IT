---
title: Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
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
ms.openlocfilehash: e4cb3a10d14f6d4c16ef9323d6e5b3c500ebc0c5
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545975"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell

Se si usa PowerShell per la gestione di Microsoft 365, è possibile avere più sessioni PowerShell aperte contemporaneamente in diverse finestre PowerShell corrispondenti alla gestione degli account utente, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e il Centro sicurezza &amp; conformità. 
  
Non si tratta di una condizione ottimale per la gestione di Microsoft 365, poiché non è possibile scambiare dati tra le finestre per la gestione dei diversi servizi. Questo argomento descrive come usare una singola istanza di PowerShell da cui gestire gli account di Microsoft 365, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams e il Centro sicurezza &amp; conformità.

>[!Note]
>Questo articolo contiene al momento solo i comandi per connettersi al cloud internazionale (+GCC). Le note forniscono collegamenti agli articoli con informazioni sulla connessione ad altri cloud di Microsoft 365.
>

## <a name="before-you-begin"></a>Prima di iniziare

Per poter gestire tutti i servizi di Microsoft 365 da una singola istanza di PowerShell, prendere in considerazione i prerequisiti seguenti:
  
- L'account aziendale o dell'Istituto di istruzione di Microsoft 365 usato per queste procedure deve avere un ruolo di amministratore di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles). Questo è un requisito per PowerShell per Microsoft 365, quindi non necessariamente per tutti gli altri servizi di Microsoft 365.
    
- È possibile usare le seguenti versioni a 64 bit di Windows:
    
  - Windows 10
    
  - Windows 8.1 o Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 o Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \*È necessario installare Microsoft .NET Framework 4.5*x* e poi Windows Management Framework 3.0 o Windows Management Framework 4.0. Per altre informazioni, vedere [Installazione di .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).
    
    È necessario utilizzare una versione a 64 bit di Windows, a causa dei requisiti, per il modulo di Skype for Business Online e una per moduli di Microsoft 365.
    
- È necessario installare i moduli necessari per Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online e Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype for Business Online, moduli PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532439)
  - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Panoramica di PowerShell per Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  PowerShell deve essere configurato per l'esecuzione di script firmati per Skype for Business Online e il Centro sicurezza &amp; conformità. A tale scopo, eseguire il comando seguente in una sessione di PowerShell con privilegi elevati (una finestra PowerShell che si apre selezionando **Esegui come amministratore**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a>Exchange Online e Centro sicurezza &amp; conformità con il modulo PowerShell V2 di Exchange Online 

In questo articolo, si usa il modulo PowerShell V2 di Exchange Online per connettersi a Exchange Online e al Centro sicurezza &amp; conformità. Al momento, tuttavia, non è possibile connettersi sia a Exchange Online che al Centro sicurezza &amp; conformità ** nella stessa finestra di PowerShell**.

Di conseguenza, è necessario scegliere una connessione con Exchange Online *o* il Centro sicurezza &amp; conformità durante la configurazione di una finestra di PowerShell per molteplici servizi Microsoft 365.

## <a name="connection-steps-when-using-just-a-password"></a>Procedura di connessione se si usa solo una password

Ecco la procedura per connettersi a tutti i servizi in una singola finestra di PowerShell se si usa solo una password per accedere.
  
1. Aprire Windows PowerShell.
    
2. Eseguire il comando seguente e immettere le credenziali dell'account aziendale o dell'Istituto di istruzione di Microsoft 365.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Eseguire il comando seguente per connettersi ad Azure AD tramite il modulo Azure Active Directory PowerShell per Graph.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   In alternativa, se si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell, eseguire il comando seguente.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in PowerShell.

4. Eseguire i comandi seguenti per la connessione a SharePoint Online. Specificare il nome dell'organizzazione per il dominio. Ad esempio, per "litwareinc.onmicrosoft.com", il valore del nome dell’organizzazione è "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. Per connettersi a Skype for Business Online eseguire i comandi seguenti. Alla prima connessione verrà visualizzato l’avviso relativo all’aumento del valore `WSMan NetworkDelayms`, che deve essere ignorato.
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Eseguire il comando seguente per connettersi a Exchange Online.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Per connettersi a Exchange Online per i cloud di Microsoft 365 diversi da quello internazionale, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

7. In alternativa, eseguire i comandi seguenti per connettersi al Centro sicurezza &amp; conformità.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Per connettersi al Centro sicurezza &amp; conformità per i cloud di Microsoft 365 diversi da quello internazionale, vedere [Connettersi al Centro sicurezza e conformità di PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

8. Eseguire i comandi seguenti per connettersi a PowerShell di Teams.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Per connettersi ai cloud di Microsoft Teams diversi da quello internazionale, vedere [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).


### <a name="azure-active-directory-powershell-for-graph-module"></a>Modulo di Azure Active Directory PowerShell per Graph

Di seguito sono elencati i comandi per tutti i servizi *ad eccezione del Centro sicurezza &amp; conformità* in un unico blocco, quando si usa il modulo di Azure Active Directory PowerShell per Graph. Specificare il nome dell’host del dominio e poi eseguirli tutti contemporaneamente.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Di seguito sono elencati i comandi per tutti i servizi *ad eccezione di Exchange Online* in un unico blocco, quando si usa il modulo di Azure Active Directory PowerShell per Graph. Specificare il nome dell’host del dominio e l’UPN per l’accesso, e poi eseguirli tutti contemporaneamente.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Modulo di Microsoft Azure Active Directory per Windows PowerShell

Di seguito sono elencati i comandi per tutti i servizi *ad eccezione del Centro sicurezza &amp; conformità* in un unico blocco, quando si usa il modulo di Microsoft Azure Active Directory per Windows PowerShell. Specificare il nome dell’host del dominio e poi eseguirli tutti contemporaneamente.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Di seguito sono elencati i comandi per tutti i servizi *ad eccezione di Exchange Online* in un unico blocco, quando si usa il modulo di Microsoft Azure Active Directory per Windows PowerShell. Specificare il nome dell’host del dominio e l’UPN per l’accesso, e poi eseguirli tutti contemporaneamente.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a>Procedura di connessione quando si usa l'autenticazione a più fattori

### <a name="azure-active-directory-powershell-for-graph-module"></a>Modulo di Azure Active Directory PowerShell per Graph

Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 *ad eccezione del Centro sicurezza &amp; conformità* con l'autenticazione a più fattori tramite il modulo di Azure Active Directory PowerShell per Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 *ad eccezione di Exchange Online* con l'autenticazione a più fattori tramite il modulo di Azure Active Directory PowerShell per Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Modulo di Microsoft Azure Active Directory per Windows PowerShell

Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 *ad eccezione del Centro sicurezza &amp; conformità* con l'autenticazione a più fattori tramite il modulo di Microsoft Azure Active Directory per Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 *ad eccezione di Exchange Online* usando l'autenticazione a più fattori tramite il modulo di Microsoft Azure Active Directory per Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Chiudere la finestra di PowerShell

Quando è tutto pronto per chiudere la finestra di PowerShell, eseguire il comando seguente per rimuovere tutte le sessioni attive in Skype for Business Online, SharePoint Online e Teams:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a>Vedere anche

- [Collegarsi a Microsoft 365 con PowerShell](connect-to-microsoft-365-powershell.md)
- [Gestire SharePoint Online con PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
