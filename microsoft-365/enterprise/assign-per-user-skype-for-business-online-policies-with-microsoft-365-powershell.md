---
title: Assegnare criteri skype for Business online per utente con PowerShell per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 'Riepilogo: usare PowerShell per Microsoft 365 per assegnare le impostazioni di comunicazione per utente con i criteri di Skype for Business online.'
ms.openlocfilehash: 6ff9fce3e0287313f6725b370b6ba89cb939eb3a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691197"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Assegnare criteri skype for Business online per utente con PowerShell per Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

L'uso di PowerShell per Microsoft 365 è un modo efficiente per assegnare impostazioni di comunicazione per utente con i criteri di Skype for Business online.
  
## <a name="prepare-to-run-the-powershell-commands"></a>Preparare l'esecuzione dei comandi di PowerShell

Utilizzare queste istruzioni per ottenere la configurazione che consenta di eseguire i comandi (ignorare i passaggi già completati):
  
1. Scaricare e installare il [Modulo di Windows PowerShell per Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366).
    
2. Aprire il prompt dei comandi Windows PowerShell ed eseguire quanto segue: 
    
```powershell
Import-Module LyncOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

Quando richiesto, immettere il nome e la password dell'account Administrator di Skype for Business online.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Aggiornamento delle impostazioni di comunicazione esterna per un account utente

Si supponga di voler modificare le impostazioni di comunicazione esterna in un account utente. Ad esempio, si desidera consentire ad Alex di comunicare con utenti federati (EnableFederationAccess è uguale a True), ma non con utenti di Windows Live (EnablePublicCloudAccess è uguale a False). A tale scopo, è necessario eseguire due operazioni:
  
1. Individuare un criterio di accesso esterno che soddisfi i criteri necessari.
    
2. Assegnare tale criterio di accesso esterno ad Alex.
    
Come si determina quale criterio di accesso esterno assegnare ad Alex? Il comando seguente restituisce tutti i criteri di accesso esterno nei quali EnableFederationAccess è impostato su True e EnablePublicCloudAccess è impostato su False:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

A meno che non siano state create istanze personalizzate di ExternalAccessPolicy, il comando restituisce un criterio che soddisfa i criteri (FederationOnly). Ecco un esempio:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Quando si conosce il criterio da assegnare ad Alex, è possibile assegnarlo utilizzando il cmdlet [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974). Di seguito viene riportato un esempio:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Assegnare un criterio è piuttosto semplice: è necessario specificare soltanto l'identità dell'utente e il nome del criterio da assegnare. 
  
Nel caso di criteri e assegnazione dei criteri, non ci si limita a effettuare operazioni con account utenti una sola volta. Ad esempio, si supponga che sia necessario disporre di un elenco di tutti gli utenti che possono comunicare con partner federati e con gli utenti di Windows Live. È noto che a tali utenti è stato assegnato il criterio di accesso utente esterno FederationAndPICDefault. Dal momento che si conosce tale informazione, è possibile visualizzare un elenco di tutti gli utenti eseguendo un comando semplice. Di seguito viene riportato il comando:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

in altre parole, è possibile visualizzare tutti gli utenti per i quali la proprietà ExternalAccessPolicy è impostata su FederationAndPICDefault. Per limitare la quantità di informazioni che vengono visualizzate sullo schermo, utilizzare il cmdlet Select-Object per visualizzare soltanto il nome di ogni utente. 
  
Per configurare tutti gli account utente affinché utilizzino quello stesso criterio, usare questo comando:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Il comando utilizza Get-CsOnlineUser per restituire una raccolta di tutti gli utenti che sono stati abilitati per Lync. In seguito, invia tutte le informazioni su Grant-CsExternalAccessPolicy che assegna il criterio FederationAndPICDefault a tutti gli utenti presenti nella raccolta.
  
Come esempio aggiuntivo, si supponga di aver assegnato in precedenza il criterio FederationAndPICDefault ad Alex, ma ora si desidera che Alex sia gestito dal criterio di accesso esterno globale. Non è possibile assegnare in modo esplicito il criterio globale. Il criterio globale viene invece utilizzato per un determinato utente se a tale utente non è assegnato alcun criterio per utente. Pertanto, se si desidera che Alex sia gestito dal criterio globale, è necessario  *non assegnare*  i criteri per utente assegnati in precedenza all'utente. Ecco un esempio di comando:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Il comando imposta il nome del criterio di accesso esterno assegnato ad Alex su un valore ($Null). Null vuol dire "niente". In altre parole, nessun criterio di accesso esterno viene assegnato ad Alex. Se non viene assegnato alcun criterio di accesso esterno a un utente, quest'ultimo viene gestito dal criterio globale.
  

## <a name="managing-large-numbers-of-users"></a>Gestione di un numero elevato di utenti

Per gestire un numero elevato di utenti (1000 o più), è necessario batch dei comandi tramite un blocco di script utilizzando il cmdlet [Invoke-Command.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7)  Negli esempi precedenti, ogni volta che viene eseguito un cmdlet, è necessario configurare la chiamata e quindi attendere il risultato prima di inviarlo di nuovo.  Quando si utilizza un blocco di script, i cmdlet possono essere eseguiti in remoto e, una volta completati, inviare nuovamente i dati. 

```powershell
Import-Module LyncOnlineConnector
$sfbSession = New-CsOnlineSession
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

In questo modo verranno trovati 500 utenti alla volta che non dispongono di un criterio client. Concederà loro il criterio client "ClientPolicyNoIMURL" e il criterio di accesso esterno "FederationAndPicDefault". I risultati vengono suddivisi in gruppi di 50 e ogni batch di 50 viene quindi inviato al computer remoto.
  
## <a name="see-also"></a>Vedere anche

[Gestire Skype for Business Online con PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
