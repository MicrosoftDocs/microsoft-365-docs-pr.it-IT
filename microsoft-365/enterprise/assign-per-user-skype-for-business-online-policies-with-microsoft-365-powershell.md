---
title: Assegnare criteri Skype for Business online per utente con PowerShell per Microsoft 365
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
description: 'Riepilogo: utilizzare PowerShell per Microsoft 365 per assegnare impostazioni di comunicazione per utente con Skype for Business criteri online.'
ms.openlocfilehash: d7f369e96f3db95c741e6d4f2178eaf9032ab0bb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288084"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="da26c-103">Assegnare criteri Skype for Business online per utente con PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da26c-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="da26c-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="da26c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="da26c-105">L'uso di PowerShell Microsoft 365 è un modo efficiente per assegnare le impostazioni di comunicazione per utente con i criteri Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="da26c-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="da26c-106">Preparare l'esecuzione dei comandi di PowerShell</span><span class="sxs-lookup"><span data-stu-id="da26c-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="da26c-107">Utilizzare queste istruzioni per ottenere la configurazione che consenta di eseguire i comandi (ignorare i passaggi già completati):</span><span class="sxs-lookup"><span data-stu-id="da26c-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="da26c-108">Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente.</span><span class="sxs-lookup"><span data-stu-id="da26c-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="da26c-109">Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="da26c-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="da26c-110">Installare il [modulo di PowerShell di Teams](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="da26c-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="da26c-111">Aprire il prompt dei comandi Windows PowerShell ed eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="da26c-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="da26c-112">Quando richiesto, immettere il nome e la password dell'account Administrator di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="da26c-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="da26c-113">Aggiornamento delle impostazioni di comunicazione esterna per un account utente</span><span class="sxs-lookup"><span data-stu-id="da26c-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="da26c-p102">Si supponga di voler modificare le impostazioni di comunicazione esterna in un account utente. Ad esempio, si desidera consentire ad Alex di comunicare con utenti federati (EnableFederationAccess è uguale a True), ma non con utenti di Windows Live (EnablePublicCloudAccess è uguale a False). A tale scopo, è necessario eseguire due operazioni:</span><span class="sxs-lookup"><span data-stu-id="da26c-p102">Suppose you want to change external communication settings on a user account. For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False). To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="da26c-117">Individuare un criterio di accesso esterno che soddisfi i criteri necessari.</span><span class="sxs-lookup"><span data-stu-id="da26c-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="da26c-118">Assegnare tale criterio di accesso esterno ad Alex.</span><span class="sxs-lookup"><span data-stu-id="da26c-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="da26c-119">Come si determina quale criterio di accesso esterno assegnare ad Alex?</span><span class="sxs-lookup"><span data-stu-id="da26c-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="da26c-120">Il comando seguente restituisce tutti i criteri di accesso esterno nei quali EnableFederationAccess è impostato su True e EnablePublicCloudAccess è impostato su False:</span><span class="sxs-lookup"><span data-stu-id="da26c-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="da26c-121">A meno che non siano state create istanze personalizzate di ExternalAccessPolicy, il comando restituisce un criterio che soddisfa i criteri (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="da26c-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="da26c-122">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="da26c-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="da26c-p105">Quando si conosce il criterio da assegnare ad Alex, è possibile assegnarlo utilizzando il cmdlet [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy). Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="da26c-p105">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet. Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="da26c-125">Assegnare un criterio è piuttosto semplice: è necessario specificare soltanto l'identità dell'utente e il nome del criterio da assegnare.</span><span class="sxs-lookup"><span data-stu-id="da26c-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="da26c-p106">Nel caso di criteri e assegnazione dei criteri, non ci si limita a effettuare operazioni con account utenti una sola volta. Ad esempio, si supponga che sia necessario disporre di un elenco di tutti gli utenti che possono comunicare con partner federati e con gli utenti di Windows Live. È noto che a tali utenti è stato assegnato il criterio di accesso utente esterno FederationAndPICDefault. Dal momento che si conosce tale informazione, è possibile visualizzare un elenco di tutti gli utenti eseguendo un comando semplice. Di seguito viene riportato il comando:</span><span class="sxs-lookup"><span data-stu-id="da26c-p106">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time. For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users. We already know that those users have been assigned the external user access policy FederationAndPICDefault. Because we know that, you can display a list of all those users by running one simple command. Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="da26c-p107">in altre parole, è possibile visualizzare tutti gli utenti per i quali la proprietà ExternalAccessPolicy è impostata su FederationAndPICDefault. Per limitare la quantità di informazioni che vengono visualizzate sullo schermo, utilizzare il cmdlet Select-Object per visualizzare soltanto il nome di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="da26c-p107">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault. (And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="da26c-133">Per configurare tutti gli account utente affinché utilizzino quello stesso criterio, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="da26c-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="da26c-134">Il comando utilizza Get-CsOnlineUser per restituire una raccolta di tutti gli utenti che sono stati abilitati per Lync. In seguito, invia tutte le informazioni su Grant-CsExternalAccessPolicy che assegna il criterio FederationAndPICDefault a tutti gli utenti presenti nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="da26c-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="da26c-135">Come esempio aggiuntivo, si supponga di aver assegnato in precedenza il criterio FederationAndPICDefault ad Alex, ma ora si desidera che Alex sia gestito dal criterio di accesso esterno globale.</span><span class="sxs-lookup"><span data-stu-id="da26c-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="da26c-136">Non è possibile assegnare in modo esplicito il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="da26c-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="da26c-137">Il criterio globale viene invece utilizzato per un determinato utente se a tale utente non è assegnato alcun criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="da26c-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="da26c-138">Pertanto, se si desidera che Alex sia gestito dal criterio globale, è necessario  *non assegnare*  i criteri per utente assegnati in precedenza all'utente.</span><span class="sxs-lookup"><span data-stu-id="da26c-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="da26c-139">Ecco un esempio di comando:</span><span class="sxs-lookup"><span data-stu-id="da26c-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="da26c-p109">Il comando imposta il nome del criterio di accesso esterno assegnato ad Alex su un valore ($Null). Null vuol dire "niente". In altre parole, nessun criterio di accesso esterno viene assegnato ad Alex. Se non viene assegnato alcun criterio di accesso esterno a un utente, quest'ultimo viene gestito dal criterio globale.</span><span class="sxs-lookup"><span data-stu-id="da26c-p109">This command sets the name of the external access policy assigned to Alex to a null value ($Null). Null means "nothing". In other words, no external access policy is assigned to Alex. When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="da26c-144">Gestione di un numero elevato di utenti</span><span class="sxs-lookup"><span data-stu-id="da26c-144">Managing large numbers of users</span></span>

<span data-ttu-id="da26c-145">Per gestire un numero elevato di utenti (1000 o più), è necessario batch i comandi tramite un blocco di script utilizzando il cmdlet [Invoke-Command.](/powershell/module/microsoft.powershell.core/invoke-command)</span><span class="sxs-lookup"><span data-stu-id="da26c-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>  <span data-ttu-id="da26c-146">Negli esempi precedenti, ogni volta che viene eseguito un cmdlet, è necessario configurare la chiamata e quindi attendere il risultato prima di inviarlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="da26c-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="da26c-147">Quando si utilizza un blocco di script, in questo modo i cmdlet possono essere eseguiti in remoto e, una volta completati, inviare di nuovo i dati.</span><span class="sxs-lookup"><span data-stu-id="da26c-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span>

```powershell
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

<span data-ttu-id="da26c-148">In questo modo verranno trovati 500 utenti alla volta che non dispongono di un criterio client.</span><span class="sxs-lookup"><span data-stu-id="da26c-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="da26c-149">Concederà loro il criterio client "ClientPolicyNoIMURL" e il criterio di accesso esterno "FederationAndPicDefault".</span><span class="sxs-lookup"><span data-stu-id="da26c-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="da26c-150">I risultati vengono suddivisi in batch in gruppi di 50 e ogni batch di 50 viene quindi inviato al computer remoto.</span><span class="sxs-lookup"><span data-stu-id="da26c-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da26c-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da26c-151">See also</span></span>

[<span data-ttu-id="da26c-152">Gestire Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="da26c-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da26c-153">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="da26c-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da26c-154">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da26c-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)