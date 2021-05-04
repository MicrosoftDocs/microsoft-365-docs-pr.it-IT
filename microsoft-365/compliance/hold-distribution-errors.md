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
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860387"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="e09bc-103">Risoluzione dei problemi di blocco di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e09bc-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="e09bc-104">In questo articolo vengono illustrati i problemi comuni che possono verificarsi con i blocchi di eDiscovery e come risolverli.</span><span class="sxs-lookup"><span data-stu-id="e09bc-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="e09bc-105">L'articolo include inoltre procedure consigliate per ridurre o evitare questi problemi.</span><span class="sxs-lookup"><span data-stu-id="e09bc-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="e09bc-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="e09bc-106">Recommended practices</span></span>

<span data-ttu-id="e09bc-107">Per ridurre il numero di errori correlati ai blocchi di eDiscovery, è consigliabile eseguire le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="e09bc-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="e09bc-108">Se una distribuzione del blocco è ancora in sospeso, con stato o , attendere il completamento della distribuzione del blocco prima di `On (Pending)` `Off (Pending)` apportare ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e09bc-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="e09bc-109">Unire gli aggiornamenti a un blocco di eDiscovery in una singola richiesta in blocco anziché aggiornare ripetutamente il criterio di blocco per ogni transazione.</span><span class="sxs-lookup"><span data-stu-id="e09bc-109">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="e09bc-110">Ad esempio, per aggiungere più cassette postali utente a un criterio di blocco esistente utilizzando il cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) eseguire il comando (o aggiungere come blocco di codice a uno script) in modo che venga eseguito una sola volta per aggiungere più utenti.</span><span class="sxs-lookup"><span data-stu-id="e09bc-110">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="e09bc-111">**Valido**</span><span class="sxs-lookup"><span data-stu-id="e09bc-111">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="e09bc-112">**Non valido**</span><span class="sxs-lookup"><span data-stu-id="e09bc-112">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="e09bc-113">Nell'esempio errato precedente, il cmdlet viene eseguito cinque volte separate per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="e09bc-113">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="e09bc-114">Per ulteriori informazioni sulle procedure consigliate per l'aggiunta di utenti a un criterio di blocco, vedere [la sezione Ulteriori](#more-information) informazioni.</span><span class="sxs-lookup"><span data-stu-id="e09bc-114">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="e09bc-115">Prima di contattare il supporto Tecnico Microsoft sui problemi di blocco di eDiscovery, seguire i passaggi descritti nella sezione [Errore/problema:](#errorissue-holds-dont-sync) I blocchi non vengono sincronizzati per ritentare la distribuzione del blocco.</span><span class="sxs-lookup"><span data-stu-id="e09bc-115">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="e09bc-116">Questo processo spesso risolve problemi temporanei, tra cui errori interni del server.</span><span class="sxs-lookup"><span data-stu-id="e09bc-116">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="e09bc-117">Errore/problema: i blocchi non vengono sincronizzati</span><span class="sxs-lookup"><span data-stu-id="e09bc-117">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="e09bc-118">Se viene visualizzato uno dei seguenti messaggi di errore quando si mettono in attesa i custodi e le origini dati, utilizzare la procedura di risoluzione per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="e09bc-118">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="e09bc-119">Risorse: la distribuzione del criterio richiede più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="e09bc-119">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="e09bc-120">L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi controllare di nuovo tra un paio d'ore.</span><span class="sxs-lookup"><span data-stu-id="e09bc-120">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="e09bc-121">Impossibile distribuire i criteri nell'origine contenuto a causa di un problema temporaneo Office 365 datacenter.</span><span class="sxs-lookup"><span data-stu-id="e09bc-121">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="e09bc-122">Il criterio corrente non viene applicato ad alcun contenuto nell'origine, quindi non c'è alcun impatto dalla distribuzione bloccata.</span><span class="sxs-lookup"><span data-stu-id="e09bc-122">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="e09bc-123">Per risolvere il problema, provare a ridistribuire il criterio.</span><span class="sxs-lookup"><span data-stu-id="e09bc-123">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="e09bc-124">Non è stato possibile eseguire le modifiche richieste al criterio a causa di un errore temporaneo del server interno.</span><span class="sxs-lookup"><span data-stu-id="e09bc-124">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="e09bc-125">Riprovare tra 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="e09bc-125">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="e09bc-126">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="e09bc-126">Resolution</span></span>

1. <span data-ttu-id="e09bc-127">Connessione [a PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) sicurezza e conformità ed eseguire il comando seguente per un blocco di eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="e09bc-127">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="e09bc-128">Esaminare il valore nel *parametro DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="e09bc-128">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="e09bc-129">Cercare errori simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="e09bc-129">Look for errors like the following:</span></span>

   > <span data-ttu-id="e09bc-130">Errore: risorse: la distribuzione del criterio richiede più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="e09bc-130">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="e09bc-131">L'aggiornamento dello stato finale della distribuzione potrebbe richiedere altre 2 ore, quindi controllare di nuovo tra un paio d'ore.</span><span class="sxs-lookup"><span data-stu-id="e09bc-131">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="e09bc-132">Provare a eseguire **il comando Set-CaseHoldPolicy -RetryDistribution** sul criterio di conservazione in questione. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="e09bc-132">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a><span data-ttu-id="e09bc-133">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="e09bc-133">More information</span></span>

- <span data-ttu-id="e09bc-134">Le indicazioni sull'aggiornamento dei criteri di blocco per più utenti nella sezione "Procedure consigliate" derivano dal fatto che il sistema blocca gli aggiornamenti simultanei a un criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="e09bc-134">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="e09bc-135">Ciò significa che quando un criterio di conservazione aggiornato viene applicato a nuovi percorsi di contenuto e il criterio di conservazione è in sospeso, non è possibile aggiungere ulteriori percorsi di contenuto al criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="e09bc-135">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="e09bc-136">Ecco alcuni aspetti da tenere presenti per ridurre il problema:</span><span class="sxs-lookup"><span data-stu-id="e09bc-136">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
  - <span data-ttu-id="e09bc-137">Ogni volta che un blocco viene aggiornato, passa immediatamente allo stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="e09bc-137">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="e09bc-138">Lo stato in sospeso indica che il blocco viene applicato ai percorsi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="e09bc-138">The pending state status means the hold is being applied to content locations.</span></span>
  
  - <span data-ttu-id="e09bc-139">Se si dispone di uno script che esegue un ciclo e aggiunge percorsi ai criteri uno alla volta (in modo analogo all'esempio non corretto mostrato nella sezione "Procedure consigliate"), il primo percorso del contenuto (ad esempio, una cassetta postale utente) avvia il processo di sincronizzazione che attiva lo stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="e09bc-139">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="e09bc-140">Ciò significa che gli altri utenti aggiunti al criterio nei cicli successivi comportano un errore.</span><span class="sxs-lookup"><span data-stu-id="e09bc-140">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
  - <span data-ttu-id="e09bc-141">Se l'organizzazione utilizza uno script che esegue un ciclo per aggiornare i percorsi del contenuto per un criterio di blocco, è necessario aggiornare lo script in modo che aggiorne i percorsi in una singola operazione in blocco (come illustrato nell'esempio corretto nella sezione "Procedure consigliate").</span><span class="sxs-lookup"><span data-stu-id="e09bc-141">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
