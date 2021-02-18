---
title: Collegare Microsoft 365 con PowerShell
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
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Connettersi al tenant di Microsoft 365 con PowerShell per Microsoft 365 per eseguire attività dell'interfaccia di amministrazione tramite riga di comando.
ms.openlocfilehash: 0691304a2d40f7ae4262e6761902f16b4f6d5ee2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288114"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Collegare Microsoft 365 con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

PowerShell per Microsoft 365 consente di gestire le impostazioni di Microsoft 365 dalla riga di comando. Per connettersi PowerShell basta installare il software richiesto e quindi connettersi alla propria organizzazione di Microsoft 365.

Sono disponibili due versioni del modulo PowerShell che è possibile usare per connettersi a Microsoft 365 e amministrare gli account utente, i gruppi e le licenze:

- Azure Active Directory PowerShell per Graph, i cui cmdlet includono *AzureAD* nel nome
- Modulo di Microsoft Azure Active Directory per Windows PowerShell, i cui cmdlet includono *MSol* nel nome.

Attualmente il modulo di Azure Active Directory PowerShell per Graph non sostituisce completamente le funzionalità del Modulo di Microsoft Azure Active Directory per Windows PowerShell per l'amministrazione di utenti, gruppi e licenze. In alcuni casi, è necessario usare entrambe le versioni. È possibile installare tranquillamente entrambe le versioni nello stesso computer.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare


**Sistema operativo**

È necessario usare versione a 64 bit di Windows. Il supporto della versione a 32 bit del Modulo di Microsoft Azure Active Directory per Windows PowerShell è terminato nel 2014.

È possibile utilizzare le seguenti versioni di Windows:
    
  - Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1

>[!Note]
>Per Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 e Windows Server 2008 R2 SP1, scaricare e installare [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).

**PowerShell**

- Per il modulo di Azure Active Directory PowerShell per Graph, è necessario usare PowerShell versione 5.1 o successive.

- Per il Modulo di Microsoft Azure Active Directory per Windows PowerShell, è necessario usare PowerShell versione 5.1 o successive fino alla versione 6. Non è possibile usare la versione 7 di PowerShell.
       
>[!Note]
>Queste procedure sono destinate agli utenti membri di un ruolo di amministratore di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://go.microsoft.com/fwlink/p/?LinkId=532367).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Connettersi con il modulo di Azure Active Directory PowerShell per Graph

I comandi nel modulo di Azure Active Directory PowerShell per Graph hanno *AzureAD* nel nome del cmdlet. È possibile installare il [modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) o [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).

Per le procedure che richiedono i nuovi cmdlet nel modulo di Azure Active Directory PowerShell per Graph, seguire questi passaggi per installare il modulo e connettersi alla sottoscrizione di Microsoft 365.

> [!Note]
> Per informazioni sul supporto per le altre versioni di Windows, vedere [Modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

### <a name="step-1-install-the-required-software"></a>Passaggio 1: installare il software necessario

È necessario eseguire questi passaggi nel computer una sola volta. Tuttavia, è probabile che sia necessario aggiornare periodicamente il software.
  
1. Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).
    
2. Eseguire questo comando:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   Se viene richiesto di installare un modulo da un archivio non attendibile, digitare **Y** e premere INVIO.

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Passaggio 2: connettersi ad Azure AD per l'abbonamento a Microsoft 365

Per connettersi ad Azure Active Directory (Azure AD) per l'abbonamento a Microsoft 365 con un nome account e una password oppure con l'autenticazione a più fattori (MFA), eseguire uno di questi comandi da un prompt dei comandi di Windows PowerShell (non necessariamente con privilegi elevati).

| Cloud di Office 365 | Comando |
|:-------|:-----|
| Office 365 internazionale (+GCC) | `Connect-AzureAD` |
| Office 365 gestito da 21 Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| U.S. Government DoD di Office 365 e U.S. Government GCC High di Office 365 | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

Nella finestra di dialogo per **accedere all'account**, digitare nome utente e password dell'account aziendale o dell'istituto di istruzione di Microsoft 365, quindi fare clic su **OK**.

Se si utilizza l'autenticazione a più fattori, seguire le istruzioni per fornire ulteriori informazioni di autenticazione, ad esempio un codice di verifica.

Dopo aver eseguito la connessione, è possibile usare i cmdlet per il [modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/module/azuread).

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Connettersi con il Modulo di Microsoft Azure Active Directory per Windows PowerShell

>[!Note]
>I cmdlet nel Modulo di Microsoft Azure Active Directory per Windows PowerShell hanno *MSol* nel nome.

PowerShell versione 7 e successive non supportano il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome. Per PowerShell versione 7 e successive, è necessario usare il modulo di Azure Active Directory PowerShell per Graph o Azure PowerShell.

PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome. Eseguire questi cmdlet da Windows PowerShell.
    
### <a name="step-1-install-the-required-software"></a>Passaggio 1: installare il software necessario

È necessario eseguire questi passaggi nel computer una sola volta. Tuttavia, è probabile che sia necessario aggiornare periodicamente il software.
  
1.  Se non si esegue Windows 10, installare la versione a 64 bit dell'Assistente per l'accesso a Microsoft Online Services: [Assistente per l'accesso a Microsoft Online Services per professionisti IT - RTW](https://www.microsoft.com/Download/details.aspx?id=28177).
    
2. Seguire questa procedura per installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell:
    
   1. Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).
   1.  Eseguire il comando **Install-Module MSOnline**.
   1. Se viene richiesto di installare il provider NuGet, digitare **Y** e premere INVIO.
   1. Se viene richiesto di installare il modulo da PSGallery, digitare **Y** e premere INVIO.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Passaggio 2: connettersi ad Azure AD per l'abbonamento a Microsoft 365

Per connettersi ad Azure AD per l'abbonamento a Microsoft 365 con un nome account e una password oppure con l'autenticazione a più fattori (MFA), eseguire uno di questi comandi da un prompt dei comandi di Windows PowerShell (non necessariamente con privilegi elevati).

| Cloud di Office 365 | Comando |
|:-------|:-----|
| Office 365 internazionale (+GCC) | `Connect-MsolService` |
| Office 365 gestito da 21 Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| U.S. Government DoD di Office 365 e U.S. Government GCC High di Office 365 | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

Nella finestra di dialogo per **accedere all'account**, digitare nome utente e password dell'account aziendale o dell'istituto di istruzione di Microsoft 365, quindi fare clic su **OK**.

Se si utilizza l'autenticazione a più fattori, seguire le istruzioni per fornire ulteriori informazioni di autenticazione, ad esempio un codice di verifica.

### <a name="how-do-you-know-it-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Se non viene visualizzato un messaggio di errore, la connessione è riuscita. Per un rapido test, eseguire un cmdlet di Microsoft 365, ad esempio, **Get-MsolUser** e vedere i risultati.
  
Se viene visualizzato un messaggio di errore, controllare i problemi seguenti:
  
- **Un problema comune è l'uso di una password errata**. Eseguire di nuovo il [Passaggio 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) e prestare particolare attenzione al nome utente e alla password immessi.
    
- **Il Modulo di Microsoft Azure Active Directory per Windows PowerShell richiede che Microsoft .NET Framework 3.5.* x* sia abilitato nel computer**. È probabile che nel computer sia installata una versione più recente, ad esempio 4 o 4.5.* x*. La compatibilità con le versioni precedenti di .NET Framework può però essere abilitata o disabilitata. Per altre informazioni, vedere gli articoli seguenti:
    
  - Per Windows Server 2012 o Windows Server 2012 R2, vedere [Abilitare .NET Framework 3.5 con Aggiunta guidata ruoli e funzionalità](https://go.microsoft.com/fwlink/p/?LinkId=532368).
    
  - Per Windows 7 o Windows Server 2008 R2, vedere [Impossibile aprire il Modulo di Azure Active Directory per Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).

  - Per Windows 10, Windows 8.1 e Windows 8, vedere [Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).

  
- **La versione di Microsoft Azure Active Directory Module per Windows PowerShell in uso potrebbe essere obsoleta.** Per verificarlo, eseguire il seguente comando in PowerShell per Microsoft 365 o il modulo di Microsoft Azure Active Directory per Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Se il numero di versione restituito è inferiore a *1.0.8070.2*, disinstallare il Modulo di Microsoft Azure Active Directory per Windows PowerShell e ripetere l'installazione dal [Passaggio 1](#step-1-install-the-required-software).

- **Se viene visualizzato un errore di connessione**, vedere [Errore "Connect-MsolService: si è verificata un'eccezione di tipo"](https://go.microsoft.com/fwlink/p/?LinkId=532377).
    
- **Se viene visualizzato un messaggio di errore "Get-Item: impossibile trovare il percorso", eseguire questo comando:**


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a>Vedere anche

- [Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Effettuare la connessione a tutti i servizi Office 365 in un'unica finestra di Windows PowerShell](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
