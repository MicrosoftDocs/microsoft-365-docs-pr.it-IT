---
title: Connettersi ai tenant Exchange Online con Windows PowerShell remoto per i partner di DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 'Sintesi: utilizzare Windows PowerShell remoto per connettersi a Exchange Online tramite il valore DelegatedOrg.'
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691307"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Connettersi ai tenant Exchange Online con Windows PowerShell remoto per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

> [!IMPORTANT]
> Le procedure descritte in questo argomento sono valide solo per i partner di autorizzazione accesso delegato (DAP). Se non si è un partner DAP, non usare le procedure descritte in questo argomento. 
  
I partner DAP sono partner di Syndication e Cloud Solution Providers (CSP). Di solito, rappresentano fornitori di rete o telecomunicazioni di altre aziende. Consentono di raggruppare le sottoscrizioni nelle offerte di servizio per i clienti. Possiedono un contratto di locazione dei partner che viene automaticamente concesso amministrare per conto di (AOBO) le autorizzazioni per i propri clienti Microsoft 365 locazione in modo che possano amministrare e riferire su tutti i loro clienti locazione.

DAP Partners è in grado di utilizzare Exchange Online PowerShell per gestire le impostazioni di Exchange Online dei clienti e ottenere i report di Microsoft 365 dalla riga di comando. È possibile usare Windows PowerShell in un computer locale per creare una sessione di PowerShell remota in Exchange Online. Si tratta di un semplice processo in tre passaggi in cui immettere le credenziali, fornire le impostazioni di connessione necessarie e quindi importare i cmdlet di Exchange Online nella sessione locale di Windows PowerShell in modo che sia possibile utilizzarli.

> [!NOTE]
> Non è possibile per i partner DAP usare le procedure descritte in [Connettersi a Exchange Online PowerShell utilizzando l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) per connettersi alle organizzazioni tenant dei clienti in Exchange Online PowerShell. MFA e Exchange Online Remote PowerShell Module non funzionano con l'autenticazione delegata.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Tempo stimato per il completamento: 5 minuti

- È possibile utilizzare le seguenti versioni di Windows:
    
  - Windows 10

  - Windows 8.1

  - Windows Server 2016

  - Windows Server 2012 o Windows Server 2012 R2

  - Windows 7 Service Pack 1 (SP1)<sup>*</sup>

  - Windows Server 2008 R2 SP1<sup>*</sup>

    <sup>*</sup> Per le versioni precedenti di Windows, è necessario installare Microsoft.NET Framework 4.5 o versione successiva e quindi una versione aggiornata di Windows Management Framework: 3.0, 4.0 o 5.1 (solo uno). Per ulteriori informazioni, vedere [Installazione di .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), e [Windows Management Framework 5.1](https://aka.ms/wmf5download).

- Windows PowerShell deve essere configurato per poter eseguire gli script e, per impostazione predefinita, non lo è. Durante il tentativo di connessione viene visualizzato l'errore seguente:

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  Per richiedere che tutti gli script di PowerShell scaricati da internet siano firmati da un editore attendibile, eseguire il seguente comando in una finestra di Windows PowerShell elevata (una finestra di Windows PowerShell aperta selezionando **Esegui come amministratore**):

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  È necessario configurare questa impostazione soltanto una volta sul computer e non ogni volta che si stabilisce una connessione.

- Per informazioni sui tasti di scelta rapida applicabili alle procedure in questo argomento, vedere [Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange](https://go.microsoft.com/fwlink/p/?LinkId=534017).

## <a name="connect-to-exchange-online-for-customer-organizations"></a>Connettersi a Exchange Online per le organizzazioni dei clienti

1. Nel computer locale, aprire Windows PowerShell ed eseguire il comando riportato di seguito.
    
    ```
    $UserCredential = Get-Credential
    ```

    Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, digitare il nome utente e la password di amministratore DAP, quindi fare clic su **OK**.
    
2. Sostituire _\<customer tenant domain name\>_ con il nome del dominio tenant a cui si desidera effettuare la connessione ed eseguire il comando riportato di seguito:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    Il passaggio chiave in questo comando è la specificazione del cliente per il quale effettuare l'accesso per le informazioni di report. A tale scopo, utilizzare il parametro  _ConnectionURI_ , in cui viene fornito il nome di dominio completo di FQDN come valore per `?DelegatedOrg=` . Questo valore indica l'endpoint di Exchange Online PowerShell corretto a cui connettersi. Remote PowerShell deve connettersi a Microsoft 365 Reporting nel contesto di un cliente specifico ogni volta che viene eseguito un report. Dopo aver eseguito la connessione a PowerShell di Exchange Online, tutti i comandi successivi vengono eseguiti nel contesto del cliente, che consente di accedere a tutti i report disponibili per il cliente.
    
3. Eseguire il comando riportato di seguito.
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> C'è un limite di tre sessioni simultanee che è possibile eseguire in un account. Al termine assicurarsi di chiudere la sessione remota di PowerShell. Chiudendo la finestra di Windows PowerShell senza disconnettere la sessione, si rischia di esaurire tutte le sessioni remote di PowerShell disponibili e di dover attendere la scadenza delle sessioni. Per disconnettere la sessione remota di PowerShell, eseguire il seguente comando:

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Dopo il passaggio 3, i cmdlet di Exchange Online vengono importati nella sessione locale di Windows PowerShell come indicato da una barra di avanzamento. Se non vengono visualizzati errori, la connessione è stata eseguita correttamente. Un breve test consiste nell'eseguire un cmdlet di Exchange Online (ad esempio, **Get-Mailbox**) e vedere i risultati.
  
Se non vengono visualizzati errori, controllare i requisiti seguenti:
  
- Un problema comune è rappresentato da una password errata. Eseguire di nuovi questi tre passaggi e prestare particolare attenzione al nome utente e alla password del passaggio 1.
    
- L'account utilizzato per connettersi a Exchange Online deve essere abilitato per PowerShell remoto. Per ulteriori informazioni, vedere [Abilitare o disabilitare l'accesso a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).
    
- Il traffico sulla porta TCP 80 deve essere aperto tra il computer locale e Exchange Online. È probabile che sia aperto, ma è bene verificare se l'organizzazione dispone di criteri restrittivi relativi all'accesso a Internet.
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a>Chiamare il cmdlet direttamente con Invoke-Command

L'importazione di una sessione remota di PowerShell (passaggio 3) può essere una procedura complessa poiché coinvolge _tutti_ i cmdlet di Exchange Online. Questo può essere un problema nell'elaborazione batch (ad esempio, quando si eseguono report o si apportano modifiche in blocco per tenant diversi). Come alternativa all'utilizzo di **Import-PSSession**, è possibile chiamare direttamente i cmdlet che si desidera usare con **Invoke-Command**. Ad esempio, per chiamare il cmdlet **Get-Mailbox**, sostituire la sintassi per il comando `Import-PSSession $Session` nel passaggio 3:
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a>Ulteriori cmdlet di report

I cmdlet utilizzati in questo argomento sono cmdlet di Windows PowerShell. Per ulteriori informazioni su questi cmdlet, vedere i seguenti argomenti:
  
- [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [Nuovo PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [Importa PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [Rimuovi PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [Set-ExecutionPolicy](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

