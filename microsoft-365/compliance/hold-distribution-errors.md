---
title: Risoluzione dei problemi di blocco di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Risolvere gli errori correlati alle esenzioni legali applicate ai custodi e alle origini dati non depositario in Core eDiscovery.
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538472"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a>Risoluzione dei problemi di blocco di eDiscovery

In questo articolo vengono illustrati i problemi comuni che possono verificarsi con i blocchi di eDiscovery e come risolverli. L'articolo include inoltre procedure consigliate per ridurre o evitare questi problemi.

## <a name="recommended-practices"></a>Procedure consigliate

Per ridurre il numero di errori correlati ai blocchi di eDiscovery, è consigliabile eseguire le procedure seguenti:

- Se una distribuzione del blocco è ancora in sospeso, con stato o , attendere il completamento della distribuzione del blocco prima di `On (Pending)` `Off (Pending)` apportare ulteriori aggiornamenti.

- Verificare se un criterio di blocco è in sospeso prima di apportare ulteriori aggiornamenti. Eseguire i comandi seguenti o salvarli in uno script di PowerShell.

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- Unire gli aggiornamenti a un blocco di eDiscovery in una singola richiesta in blocco anziché aggiornare ripetutamente il criterio di blocco per ogni transazione. Ad esempio, per aggiungere più cassette postali utente a un criterio di blocco esistente utilizzando il cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) eseguire il comando (o aggiungere come blocco di codice a uno script) in modo che venga eseguito una sola volta per aggiungere più utenti.

  **Valido**

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **Non valido**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   Nell'esempio errato precedente, il cmdlet viene eseguito cinque volte separate per completare l'attività. Per ulteriori informazioni sulle procedure consigliate per l'aggiunta di utenti a un criterio di blocco, vedere [la sezione Ulteriori](#more-information) informazioni.

- Prima di contattare il supporto Tecnico Microsoft sui problemi di blocco di eDiscovery, seguire i passaggi descritti nella sezione [Errore/problema:](#errorissue-holds-dont-sync) I blocchi non vengono sincronizzati per ritentare la distribuzione del blocco. Questo processo spesso risolve problemi temporanei, tra cui errori interni del server.

## <a name="errorissue-holds-dont-sync"></a>Errore/problema: i blocchi non vengono sincronizzati

Se viene visualizzato uno dei seguenti messaggi di errore quando si mettono in attesa i custodi e le origini dati, utilizzare la procedura di risoluzione per risolvere il problema.

> Risorse: la distribuzione del criterio richiede più tempo del previsto. L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi controllare di nuovo tra un paio d'ore.

> Impossibile distribuire i criteri nell'origine contenuto a causa di un problema temporaneo Office 365 datacenter. Il criterio corrente non viene applicato ad alcun contenuto nell'origine, quindi non c'è alcun impatto dalla distribuzione bloccata. Per risolvere il problema, provare a ridistribuire il criterio.

> Non è stato possibile eseguire le modifiche richieste al criterio a causa di un errore temporaneo del server interno. Riprovare tra 30 minuti.

### <a name="resolution"></a>Risoluzione

1. Connessione [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente per un blocco di eDiscovery:

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. Esaminare il valore nel *parametro DistributionDetail.* Cercare errori simili ai seguenti:

   > Errore: risorse: la distribuzione del criterio richiede più tempo del previsto. L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi controllare di nuovo tra un paio d'ore.

3. Provare a eseguire **il comando Set-CaseHoldPolicy -RetryDistribution** sul criterio di conservazione in questione. Per esempio:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a>Errore: il SharePoint è di sola lettura o non è accessibile

Se viene visualizzato il messaggio di errore seguente quando si bloccano i [](/sharepoint/sharepoint-admin-role) custodi e le origini dati, significa che l'amministratore globale dell'organizzazione o SharePoint ha bloccato il sito. Un sito bloccato impedisce a eDiscovery di bloccare il sito.

> Il SharePoint è di sola lettura o non è accessibile. Contattare l'amministratore del sito per rendere scrivibile il sito e quindi ridistribuire questo criterio.

### <a name="resolution"></a>Risoluzione

Sbloccare il sito (o chiedere a un amministratore di sbloccarlo) per risolvere il problema. Per ulteriori informazioni su come modificare lo stato di blocco per un sito, vedere [Lock and unlock sites.](/sharepoint/manage-lock-status)

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a>Errore: la cassetta postale o SharePoint sito potrebbe non esistere

Se viene visualizzato il messaggio di errore seguente quando si mettono in attesa i custodi e le origini dati, utilizzare la procedura di risoluzione per risolvere il problema.

> La cassetta postale o SharePoint sito potrebbe non esistere.  Se il problema non è corretto, contattare il supporto tecnico Microsoft.  In caso contrario, rimuoverlo da questo criterio.

### <a name="resolution"></a>Risoluzione

- Eseguire [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell per verificare se la cassetta postale utente esiste nell'organizzazione.

- Eseguire il cmdlet [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) in SharePoint PowerShell online per verificare se il sito esiste nell'organizzazione.

- Verificare se l'URL del sito è cambiato.

## <a name="more-information"></a>Altre informazioni

Le indicazioni sull'aggiornamento dei criteri di blocco per più utenti nella sezione "Procedure consigliate" derivano dal fatto che il sistema blocca gli aggiornamenti simultanei a un criterio di conservazione. Ciò significa che quando un criterio di conservazione aggiornato viene applicato a nuovi percorsi di contenuto e il criterio di conservazione è in sospeso, non è possibile aggiungere ulteriori percorsi di contenuto al criterio di conservazione. Ecco alcuni aspetti da tenere presenti per ridurre il problema:
  
- Ogni volta che un blocco viene aggiornato, passa immediatamente allo stato in sospeso. Lo stato in sospeso indica che il blocco viene applicato ai percorsi del contenuto.
  
- Se si dispone di uno script che esegue un ciclo e aggiunge percorsi ai criteri uno alla volta (in modo analogo all'esempio non corretto mostrato nella sezione "Procedure consigliate"), il primo percorso del contenuto (ad esempio, una cassetta postale utente) avvia il processo di sincronizzazione che attiva lo stato in sospeso. Ciò significa che gli altri utenti aggiunti al criterio nei cicli successivi comportano un errore.
  
- Se l'organizzazione utilizza uno script che esegue un ciclo per aggiornare i percorsi del contenuto per un criterio di blocco, è necessario aggiornare lo script in modo che aggiorne i percorsi in una singola operazione in blocco (come illustrato nell'esempio corretto nella sezione "Procedure consigliate").
