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
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="d4890-103">Connettersi ai tenant Exchange Online con Windows PowerShell remoto per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)</span><span class="sxs-lookup"><span data-stu-id="d4890-103">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="d4890-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d4890-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4890-p101">Le procedure descritte in questo argomento sono valide solo per i partner di autorizzazione accesso delegato (DAP). Se non si è un partner DAP, non usare le procedure descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d4890-p101">The procedures in this topic are only for Delegated Access Permission (DAP) partners. If you aren't a DAP partner, don't use the procedures in this topic.</span></span> 
  
<span data-ttu-id="d4890-107">I partner DAP sono partner di Syndication e Cloud Solution Providers (CSP).</span><span class="sxs-lookup"><span data-stu-id="d4890-107">DAP partners are Syndication and Cloud Solution Providers (CSP) partners.</span></span> <span data-ttu-id="d4890-108">Di solito, rappresentano fornitori di rete o telecomunicazioni di altre aziende.</span><span class="sxs-lookup"><span data-stu-id="d4890-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="d4890-109">Consentono di raggruppare le sottoscrizioni nelle offerte di servizio per i clienti.</span><span class="sxs-lookup"><span data-stu-id="d4890-109">They bundle subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="d4890-110">Possiedono un contratto di locazione dei partner che viene automaticamente concesso amministrare per conto di (AOBO) le autorizzazioni per i propri clienti Microsoft 365 locazione in modo che possano amministrare e riferire su tutti i loro clienti locazione.</span><span class="sxs-lookup"><span data-stu-id="d4890-110">They own a partner tenancy that is automatically granted Administer On Behalf Of (AOBO) permissions to their Microsoft 365 customer tenancies so they can administer and report on all of their customer tenancies.</span></span>

<span data-ttu-id="d4890-111">DAP Partners è in grado di utilizzare Exchange Online PowerShell per gestire le impostazioni di Exchange Online dei clienti e ottenere i report di Microsoft 365 dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d4890-111">DAP partners can use Exchange Online PowerShell to manage customer Exchange Online settings and get Microsoft 365 reports from the command line.</span></span> <span data-ttu-id="d4890-112">È possibile usare Windows PowerShell in un computer locale per creare una sessione di PowerShell remota in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d4890-112">You use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online.</span></span> <span data-ttu-id="d4890-113">Si tratta di un semplice processo in tre passaggi in cui immettere le credenziali, fornire le impostazioni di connessione necessarie e quindi importare i cmdlet di Exchange Online nella sessione locale di Windows PowerShell in modo che sia possibile utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="d4890-113">It's a simple three-step process where you enter your credentials, provide the required connection settings, and then import the Exchange Online cmdlets into your local Windows PowerShell session so that you can use them.</span></span>

> [!NOTE]
> <span data-ttu-id="d4890-p104">Non è possibile per i partner DAP usare le procedure descritte in [Connettersi a Exchange Online PowerShell utilizzando l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) per connettersi alle organizzazioni tenant dei clienti in Exchange Online PowerShell. MFA e Exchange Online Remote PowerShell Module non funzionano con l'autenticazione delegata.</span><span class="sxs-lookup"><span data-stu-id="d4890-p104">DAP partners can't use the procedures in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) to connect to their customer tenant organizations in Exchange Online PowerShell. MFA and the Exchange Online Remote PowerShell Module don't work with delegated authentication.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d4890-116">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="d4890-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d4890-117">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="d4890-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="d4890-118">È possibile utilizzare le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="d4890-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="d4890-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d4890-119">Windows 10</span></span>

  - <span data-ttu-id="d4890-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d4890-120">Windows 8.1</span></span>

  - <span data-ttu-id="d4890-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d4890-121">Windows Server 2016</span></span>

  - <span data-ttu-id="d4890-122">Windows Server 2012 o Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d4890-122">Windows Server 2012 or Windows Server 2012 R2</span></span>

  - <span data-ttu-id="d4890-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d4890-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span></span>

  - <span data-ttu-id="d4890-124">Windows Server 2008 R2 SP1<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d4890-124">Windows Server 2008 R2 SP1<sup>\*</sup></span></span>

    <span data-ttu-id="d4890-p105"><sup>\*</sup> Per le versioni precedenti di Windows, è necessario installare Microsoft.NET Framework 4.5 o versione successiva e quindi una versione aggiornata di Windows Management Framework: 3.0, 4.0 o 5.1 (solo uno). Per ulteriori informazioni, vedere [Installazione di .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), e [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span><span class="sxs-lookup"><span data-stu-id="d4890-p105"><sup>\*</sup> For older versions of Windows, you need to install the Microsoft.NET Framework 4.5 or later and then an updated version of the Windows Management Framework: 3.0, 4.0, or 5.1 (only one). For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), and [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span></span>

- <span data-ttu-id="d4890-p106">Windows PowerShell deve essere configurato per poter eseguire gli script e, per impostazione predefinita, non lo è. Durante il tentativo di connessione viene visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="d4890-p106">Windows PowerShell needs to be configured to run scripts, and by default, it isn't. You'll get the following error when you try to connect:</span></span>

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  <span data-ttu-id="d4890-129">Per richiedere che tutti gli script di PowerShell scaricati da internet siano firmati da un editore attendibile, eseguire il seguente comando in una finestra di Windows PowerShell elevata (una finestra di Windows PowerShell aperta selezionando **Esegui come amministratore**):</span><span class="sxs-lookup"><span data-stu-id="d4890-129">To require all PowerShell scripts that you download from the internet are signed by a trusted publisher, run the following command in an elevated Windows PowerShell window (a Windows PowerShell window you open by selecting **Run as administrator**):</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  <span data-ttu-id="d4890-130">È necessario configurare questa impostazione soltanto una volta sul computer e non ogni volta che si stabilisce una connessione.</span><span class="sxs-lookup"><span data-stu-id="d4890-130">You need to configure this setting only once on your computer, not every time you connect.</span></span>

- <span data-ttu-id="d4890-131">Per informazioni sui tasti di scelta rapida applicabili alle procedure in questo argomento, vedere [Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span><span class="sxs-lookup"><span data-stu-id="d4890-131">For information about keyboard shortcuts that might apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span></span>

## <a name="connect-to-exchange-online-for-customer-organizations"></a><span data-ttu-id="d4890-132">Connettersi a Exchange Online per le organizzazioni dei clienti</span><span class="sxs-lookup"><span data-stu-id="d4890-132">Connect to Exchange Online for customer organizations</span></span>

1. <span data-ttu-id="d4890-133">Nel computer locale, aprire Windows PowerShell ed eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d4890-133">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="d4890-134">Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, digitare il nome utente e la password di amministratore DAP, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4890-134">In the **Windows PowerShell Credential Request** dialog box, enter your DAP administrator user name and password, and then click **OK**.</span></span>
    
2. <span data-ttu-id="d4890-135">Sostituire _\<customer tenant domain name\>_ con il nome del dominio tenant a cui si desidera effettuare la connessione ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d4890-135">Replace _\<customer tenant domain name\>_ with the name of the tenant domain that you want to connect to, and run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    <span data-ttu-id="d4890-136">Il passaggio chiave in questo comando è la specificazione del cliente per il quale effettuare l'accesso per le informazioni di report.</span><span class="sxs-lookup"><span data-stu-id="d4890-136">The key step in this command is specifying which customer to access for the reporting information.</span></span> <span data-ttu-id="d4890-137">A tale scopo, utilizzare il parametro  _ConnectionURI_ , in cui viene fornito il nome di dominio completo di FQDN come valore per `?DelegatedOrg=` .</span><span class="sxs-lookup"><span data-stu-id="d4890-137">You do this in the  _ConnectionURI_ parameter, where you provide the FQDN of the initial domain name as the value for `?DelegatedOrg=`.</span></span> <span data-ttu-id="d4890-138">Questo valore indica l'endpoint di Exchange Online PowerShell corretto a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="d4890-138">This value indicates the correct Exchange Online PowerShell endpoint to connect to.</span></span> <span data-ttu-id="d4890-139">Remote PowerShell deve connettersi a Microsoft 365 Reporting nel contesto di un cliente specifico ogni volta che viene eseguito un report.</span><span class="sxs-lookup"><span data-stu-id="d4890-139">Remote PowerShell must connect to Microsoft 365 reporting in the context of a specific customer each time a report is run.</span></span> <span data-ttu-id="d4890-140">Dopo aver eseguito la connessione a PowerShell di Exchange Online, tutti i comandi successivi vengono eseguiti nel contesto del cliente, che consente di accedere a tutti i report disponibili per il cliente.</span><span class="sxs-lookup"><span data-stu-id="d4890-140">After you connect to Exchange Online PowerShell, all subsequent commands are run in the context of the customer, which gives you access to all of the available reports for the customer.</span></span>
    
3. <span data-ttu-id="d4890-141">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d4890-141">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> <span data-ttu-id="d4890-p108">C'è un limite di tre sessioni simultanee che è possibile eseguire in un account. Al termine assicurarsi di chiudere la sessione remota di PowerShell. Chiudendo la finestra di Windows PowerShell senza disconnettere la sessione, si rischia di esaurire tutte le sessioni remote di PowerShell disponibili e di dover attendere la scadenza delle sessioni. Per disconnettere la sessione remota di PowerShell, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="d4890-p108">There's a limit of three simultaneous sessions that can run under one account. Be sure to disconnect the remote PowerShell session when you're finished. If you close the Windows PowerShell window without disconnecting the session, you can use up all the remote PowerShell sessions available to you, and you'll need to wait for the sessions to expire. To disconnect the remote PowerShell session, run the following command:</span></span>

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d4890-146">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="d4890-146">How do you know this worked?</span></span>

<span data-ttu-id="d4890-p109">Dopo il passaggio 3, i cmdlet di Exchange Online vengono importati nella sessione locale di Windows PowerShell come indicato da una barra di avanzamento. Se non vengono visualizzati errori, la connessione è stata eseguita correttamente. Un breve test consiste nell'eseguire un cmdlet di Exchange Online (ad esempio, **Get-Mailbox**) e vedere i risultati.</span><span class="sxs-lookup"><span data-stu-id="d4890-p109">After Step 3, the Exchange Online cmdlets are imported into your local Windows PowerShell session as tracked by a progress bar. If you don't receive any errors, you connected successfully. A quick test is to run an Exchange Online cmdlet (for example, **Get-Mailbox**) and see the results.</span></span>
  
<span data-ttu-id="d4890-150">Se non vengono visualizzati errori, controllare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4890-150">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="d4890-p110">Un problema comune è rappresentato da una password errata. Eseguire di nuovi questi tre passaggi e prestare particolare attenzione al nome utente e alla password del passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d4890-p110">A common problem is an incorrect password. Run the three steps again and pay close attention to the user name and password you enter in Step 1.</span></span>
    
- <span data-ttu-id="d4890-p111">L'account utilizzato per connettersi a Exchange Online deve essere abilitato per PowerShell remoto. Per ulteriori informazioni, vedere [Abilitare o disabilitare l'accesso a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span><span class="sxs-lookup"><span data-stu-id="d4890-p111">The account you use to connect to Exchange Online must be enabled for remote PowerShell. For more information, see [Enable or disable access to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span></span>
    
- <span data-ttu-id="d4890-p112">Il traffico sulla porta TCP 80 deve essere aperto tra il computer locale e Exchange Online. È probabile che sia aperto, ma è bene verificare se l'organizzazione dispone di criteri restrittivi relativi all'accesso a Internet.</span><span class="sxs-lookup"><span data-stu-id="d4890-p112">TCP port 80 traffic needs to be open between your local computer and Exchange Online. It's probably open, but it's something to consider if your organization has a restrictive Internet access policy.</span></span>
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a><span data-ttu-id="d4890-157">Chiamare il cmdlet direttamente con Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d4890-157">Call the cmdlet directly with Invoke-Command</span></span>

<span data-ttu-id="d4890-p113">L'importazione di una sessione remota di PowerShell (passaggio 3) può essere una procedura complessa poiché coinvolge _tutti_ i cmdlet di Exchange Online. Questo può essere un problema nell'elaborazione batch (ad esempio, quando si eseguono report o si apportano modifiche in blocco per tenant diversi). Come alternativa all'utilizzo di **Import-PSSession**, è possibile chiamare direttamente i cmdlet che si desidera usare con **Invoke-Command**. Ad esempio, per chiamare il cmdlet **Get-Mailbox**, sostituire la sintassi per il comando `Import-PSSession $Session` nel passaggio 3:</span><span class="sxs-lookup"><span data-stu-id="d4890-p113">Importing a remote PowerShell session (Step 3) can be a lengthy process because it brings in _all_ Exchange Online cmdlets. This can be an issue in batch processing (for example, when you're running reports or making bulk changes for different tenants). As an alternative to using **Import-PSSession**, you can call cmdlets you want to use directly with **Invoke-Command**. For example, to call the **Get-Milbox** cmdlet, substitute this syntax for the `Import-PSSession $Session` command in Step 3:</span></span>
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a><span data-ttu-id="d4890-162">Ulteriori cmdlet di report</span><span class="sxs-lookup"><span data-stu-id="d4890-162">More reporting cmdlets</span></span>

<span data-ttu-id="d4890-p114">I cmdlet utilizzati in questo argomento sono cmdlet di Windows PowerShell. Per ulteriori informazioni su questi cmdlet, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="d4890-p114">The cmdlets that you used in this topic are Windows PowerShell cmdlets. For more information about these cmdlets, see the following topics:</span></span>
  
- [<span data-ttu-id="d4890-165">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="d4890-165">Get-Credential</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [<span data-ttu-id="d4890-166">Nuovo PSSession</span><span class="sxs-lookup"><span data-stu-id="d4890-166">New-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [<span data-ttu-id="d4890-167">Importa PSSession</span><span class="sxs-lookup"><span data-stu-id="d4890-167">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [<span data-ttu-id="d4890-168">Rimuovi PSSession</span><span class="sxs-lookup"><span data-stu-id="d4890-168">Remove-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [<span data-ttu-id="d4890-169">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="d4890-169">Set-ExecutionPolicy</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

