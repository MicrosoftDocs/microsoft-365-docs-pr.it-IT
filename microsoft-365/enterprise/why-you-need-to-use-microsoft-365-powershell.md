---
title: Perché è necessario usare PowerShell per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Riepilogo: comprendere il motivo per cui è necessario utilizzare PowerShell per gestire Microsoft 365, in alcuni casi in modo più efficiente e in altri casi per necessità.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754107"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="10332-103">Perché è necessario usare PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10332-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="10332-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="10332-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="10332-105">Con l'interfaccia di amministrazione di Microsoft 365, è possibile gestire gli account utente e le licenze di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="10332-106">È inoltre possibile gestire i servizi Microsoft 365, ad esempio Exchange Online, teams e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="10332-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="10332-107">Se invece si utilizza PowerShell per gestire questi servizi, è possibile utilizzare l'ambiente della riga di comando e del linguaggio di scripting per velocizzare, automatizzare e rendere disponibili le funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="10332-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="10332-108">In questo articolo viene illustrato come utilizzare PowerShell per gestire Microsoft 365 per:</span><span class="sxs-lookup"><span data-stu-id="10332-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="10332-109">Rivelare informazioni aggiuntive che non sono visibili nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10332-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="10332-110">Configurare le funzionalità e le impostazioni possibili solo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="10332-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="10332-111">Operazioni in blocco</span><span class="sxs-lookup"><span data-stu-id="10332-111">Do bulk operations</span></span>
    
- <span data-ttu-id="10332-112">Filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="10332-112">Filter data</span></span>
    
- <span data-ttu-id="10332-113">Stampa o salvataggio dei dati</span><span class="sxs-lookup"><span data-stu-id="10332-113">Print or save data</span></span>
    
- <span data-ttu-id="10332-114">Gestire tra i servizi</span><span class="sxs-lookup"><span data-stu-id="10332-114">Manage across services</span></span>
    
<span data-ttu-id="10332-115">Tenere presente che PowerShell per Microsoft 365 è un insieme di moduli per Windows PowerShell, che è un ambiente della riga di comando per i servizi e le piattaforme basati su Windows.</span><span class="sxs-lookup"><span data-stu-id="10332-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="10332-116">Questo ambiente crea una lingua della shell dei comandi che può essere estesa con moduli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="10332-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="10332-117">Consente di eseguire comandi o script semplici o complessi.</span><span class="sxs-lookup"><span data-stu-id="10332-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="10332-118">Ad esempio, dopo aver installato i moduli di PowerShell per Microsoft 365 e aver eseguito la connessione alla sottoscrizione Microsoft 365, è possibile eseguire il comando seguente per elencare tutte le cassette postali degli utenti per Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="10332-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="10332-119">È anche possibile ottenere l'elenco delle cassette postali utilizzando l'interfaccia di amministrazione di Microsoft 365 ma contando gli elementi in tutti gli elenchi di tutti i siti per tutte le app Web non è facile.</span><span class="sxs-lookup"><span data-stu-id="10332-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="10332-120">PowerShell per Microsoft 365 è stato creato per semplificare la gestione di Microsoft 365 e non per la sostituzione dell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="10332-121">Gli amministratori devono essere in grado di utilizzare PowerShell per Microsoft 365 perché esistono alcune procedure di configurazione che possono essere eseguite solo tramite PowerShell per i comandi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="10332-122">Per questi casi, è necessario sapere come eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10332-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="10332-123">Installare i moduli di PowerShell per Microsoft 365 (solo una volta per ogni computer di amministratore).</span><span class="sxs-lookup"><span data-stu-id="10332-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="10332-124">Connettersi alla sottoscrizione Microsoft 365 (una volta per ogni sessione di PowerShell).</span><span class="sxs-lookup"><span data-stu-id="10332-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="10332-125">Raccogliere le informazioni necessarie per eseguire i comandi di PowerShell necessari per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="10332-126">Eseguire PowerShell per i comandi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="10332-127">Dopo aver imparato queste abilità di base, non è necessario elencare gli utenti delle cassette postali utilizzando il comando **Get-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="10332-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="10332-128">Inoltre, non è necessario capire come creare un nuovo comando come indicato in precedenza per contare tutti gli elementi in tutti gli elenchi di tutti i siti per tutte le app Web.</span><span class="sxs-lookup"><span data-stu-id="10332-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="10332-129">Microsoft e la community degli amministratori possono aiutarti a svolgere le attività in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="10332-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="10332-130">PowerShell per Microsoft 365 è in grado di rivelare informazioni che non sono visibili con l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10332-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="10332-131">L'interfaccia di amministrazione di Microsoft 365 Visualizza numerose informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="10332-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="10332-132">Tuttavia, non vengono visualizzate tutte le informazioni possibili che Microsoft 365 archivia sugli utenti, le licenze, le cassette postali e i siti.</span><span class="sxs-lookup"><span data-stu-id="10332-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="10332-133">Di seguito è riportato un esempio per *gli utenti e i gruppi* nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="10332-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Esempio di visualizzazione di utenti e gruppi nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="10332-135">In questa visualizzazione vengono fornite le informazioni necessarie in molti casi.</span><span class="sxs-lookup"><span data-stu-id="10332-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="10332-136">Tuttavia, in alcuni casi sono necessarie informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="10332-136">However, there are times when you need more.</span></span> <span data-ttu-id="10332-137">Ad esempio, le licenze Microsoft 365 (e le funzionalità di Microsoft 365 disponibili per un utente) dipendono in parte dalla posizione geografica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="10332-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="10332-138">I criteri e le funzionalità che possono essere estesi a un utente che vive negli Stati Uniti potrebbero non essere uguali a quelli che è possibile estendere a un utente in India o in Belgio.</span><span class="sxs-lookup"><span data-stu-id="10332-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="10332-139">Attenersi alla seguente procedura nell'interfaccia di amministrazione di Microsoft 365 per determinare la posizione geografica di un utente:</span><span class="sxs-lookup"><span data-stu-id="10332-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="10332-140">Fare doppio clic sul **Nome visualizzato** dell'utente.</span><span class="sxs-lookup"><span data-stu-id="10332-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="10332-141">Nel riquadro di visualizzazione proprietà utente, selezionare **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="10332-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="10332-142">Nella visualizzazione dettagli, fare clic su **ulteriori dettagli**.</span><span class="sxs-lookup"><span data-stu-id="10332-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="10332-143">Scorrere fino a individuare il **paese o l'area geografica**del titolo:</span><span class="sxs-lookup"><span data-stu-id="10332-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Esempio di informazioni sull'area geografica per un utente nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="10332-145">Prendere nota del nome visualizzato e della posizione dell'utente su un pezzo di carta o copiarlo e incollarlo nel Blocco note.</span><span class="sxs-lookup"><span data-stu-id="10332-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="10332-146">È necessario ripetere questa procedura per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="10332-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="10332-147">Se si dispone di numerosi utenti, questo processo può essere noioso.</span><span class="sxs-lookup"><span data-stu-id="10332-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="10332-148">Con PowerShell per Microsoft 365, è possibile visualizzare queste informazioni per tutti gli utenti utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="10332-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="10332-149">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per il modulo di Windows PowerShell e i cmdlet che dispongono di *MSOL* nel proprio nome.</span><span class="sxs-lookup"><span data-stu-id="10332-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="10332-150">È necessario eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10332-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="10332-151">Di seguito è riportato un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="10332-151">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

<span data-ttu-id="10332-152">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente (**Get-AzureADUser**), ma visualizzare solo il nome e la posizione di ogni utente (**Select DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="10332-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="10332-153">Poiché PowerShell per Microsoft 365 supporta una lingua della shell dei comandi, è possibile modificare ulteriormente le informazioni ottenute tramite il comando **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="10332-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="10332-154">Ad esempio, potrebbe essere necessario ordinare gli utenti in base alla posizione, raggruppando tutti gli utenti brasiliani insieme, tutti gli utenti degli Stati Uniti e così via.</span><span class="sxs-lookup"><span data-stu-id="10332-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="10332-155">Di seguito è riportato il comando:</span><span class="sxs-lookup"><span data-stu-id="10332-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="10332-156">Di seguito è riportato un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="10332-156">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

<span data-ttu-id="10332-157">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente, ma visualizzare solo il nome e la posizione di ogni utente e ordinarli in primo luogo in base alla posizione e quindi al nome (**Sort UsageLocation, DisplayName**).</span><span class="sxs-lookup"><span data-stu-id="10332-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="10332-158">È inoltre possibile utilizzare ulteriori filtri.</span><span class="sxs-lookup"><span data-stu-id="10332-158">You can also use additional filtering.</span></span> <span data-ttu-id="10332-159">Ad esempio, se si desidera visualizzare tali informazioni sugli utenti residenti in Brasile, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="10332-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="10332-160">Di seguito è riportato un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="10332-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="10332-161">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente la cui posizione è il Brasile (**dove {$ \_ . UsageLocation-EQ "BR"}**), quindi vengono visualizzati il nome e la posizione di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="10332-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="10332-162">**Nota sui domini di grandi dimensioni**</span><span class="sxs-lookup"><span data-stu-id="10332-162">**A note about large domains**</span></span>
  
<span data-ttu-id="10332-163">Se si dispone di un dominio di grandi dimensioni con decine di migliaia di utenti, provare alcuni degli esempi illustrati in questo articolo potrebbe portare alla limitazione.</span><span class="sxs-lookup"><span data-stu-id="10332-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="10332-164">In base a fattori quali la potenza di calcolo e la larghezza di banda di rete disponibile, è possibile che si stia tentando di fare troppo contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="10332-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="10332-165">Per le organizzazioni di grandi dimensioni potrebbe essere necessario dividere alcune di queste operazioni di PowerShell in due comandi.</span><span class="sxs-lookup"><span data-stu-id="10332-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="10332-166">Ad esempio, il comando seguente restituisce tutti gli account utente e visualizza il nome e il percorso di ognuno di essi:</span><span class="sxs-lookup"><span data-stu-id="10332-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="10332-167">Questa operazione funziona perfettamente per i domini più piccoli.</span><span class="sxs-lookup"><span data-stu-id="10332-167">That works great for smaller domains.</span></span> <span data-ttu-id="10332-168">Tuttavia, in un'organizzazione di grandi dimensioni, potrebbe essere necessario suddividere l'operazione in due comandi: un comando per archiviare le informazioni sull'account utente in una variabile e un'altra per visualizzare le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="10332-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="10332-169">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="10332-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="10332-170">L'interpretazione di questo set di comandi di PowerShell è la seguente:</span><span class="sxs-lookup"><span data-stu-id="10332-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="10332-171">Ottenere tutti gli utenti nella sottoscrizione Microsoft 365 corrente e archiviare le informazioni in una variabile denominata $x (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="10332-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="10332-172">Visualizzare il contenuto della variabile *$x*, ma includere solo il nome e la posizione di ogni utente (**$x | Selezionare DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="10332-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="10332-173">Microsoft 365 dispone di funzionalità che è possibile configurare solo con PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10332-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="10332-174">L'interfaccia di amministrazione di Microsoft 365 ha lo scopo di consentire l'accesso a attività amministrative comuni e utili per la maggior parte degli ambienti.</span><span class="sxs-lookup"><span data-stu-id="10332-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="10332-175">In altre parole, l'interfaccia di amministrazione di Microsoft 365 è stata progettata in modo che l'amministratore tipico possa eseguire le attività di gestione più comuni.</span><span class="sxs-lookup"><span data-stu-id="10332-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="10332-176">Tuttavia, esistono alcune attività che non possono essere eseguite nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="10332-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="10332-177">Ad esempio, l'interfaccia di amministrazione di Skype for business online offre alcune opzioni per la creazione di inviti a riunioni personalizzate:</span><span class="sxs-lookup"><span data-stu-id="10332-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Esempio di visualizzazione di inviti personalizzati a riunioni nell’interfaccia di amministrazione di Skype for Business online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="10332-179">Con queste impostazioni, è possibile aggiungere un tocco di personalizzazione e professionalità alle convocazioni di riunioni.</span><span class="sxs-lookup"><span data-stu-id="10332-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="10332-180">Tuttavia, per le impostazioni di configurazione delle riunioni non è sufficiente creare inviti alle riunioni personalizzati.</span><span class="sxs-lookup"><span data-stu-id="10332-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="10332-181">Ad esempio, per impostazione predefinita le riunioni consentono:</span><span class="sxs-lookup"><span data-stu-id="10332-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="10332-182">A utenti anonimi di ottenere l'ingresso automatico a ogni riunione.</span><span class="sxs-lookup"><span data-stu-id="10332-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="10332-183">Ai partecipanti di registrare una riunione.</span><span class="sxs-lookup"><span data-stu-id="10332-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="10332-184">A tutti gli utenti dell'organizzazione di essere designati come relatori quando partecipano a riunione.</span><span class="sxs-lookup"><span data-stu-id="10332-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="10332-185">Queste impostazioni non sono disponibili nell'interfaccia di amministrazione di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="10332-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="10332-186">È possibile controllarli da PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="10332-187">Di seguito viene riportato un comando che disabilita queste tre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="10332-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="10332-188">Per eseguire questo comando, è necessario installare il [modulo di PowerShell di Skype for business online ](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="10332-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="10332-189">L'interpretazione di questo comando di PowerShell è la seguente:</span><span class="sxs-lookup"><span data-stu-id="10332-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="10332-190">Nelle impostazioni per le nuove riunioni di Skype for business online (**Set-CsMeetingConfiguration**), disabilitare la possibilità di consentire agli utenti anonimi di ottenere l'accesso automatico alle riunioni (**-AdmitAnonymousUsersByDefault $false**).</span><span class="sxs-lookup"><span data-stu-id="10332-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="10332-191">Disabilitare la possibilità per i partecipanti di registrare le riunioni (**-AllowConferenceRecording $false**).</span><span class="sxs-lookup"><span data-stu-id="10332-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="10332-192">Non designare tutti gli utenti dell'organizzazione come relatori (**-DesignateAsPresenter "None"**).</span><span class="sxs-lookup"><span data-stu-id="10332-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="10332-193">Per ripristinare le impostazioni predefinite (abilitare le opzioni), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="10332-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="10332-194">Esistono anche altri scenari analoghi, che è il motivo per cui gli amministratori dovrebbero sapere come eseguire PowerShell per i comandi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="10332-195">PowerShell per Microsoft 365 è ideale per le operazioni in blocco</span><span class="sxs-lookup"><span data-stu-id="10332-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="10332-196">Le interfacce visive come l'interfaccia di amministrazione di Microsoft 365 sono estremamente utili quando si ha a che fare con un'unica operazione.</span><span class="sxs-lookup"><span data-stu-id="10332-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="10332-197">Ad esempio, se è necessario disabilitare un account utente, è possibile utilizzare l'interfaccia di amministrazione per individuare e cancellare rapidamente una casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="10332-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="10332-198">Potrebbe essere più facile che eseguire un'operazione analoga in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10332-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="10332-199">Tuttavia, se è necessario modificare molte cose o alcuni elementi selezionati all'interno di un insieme di grandi dimensioni, è possibile che l'interfaccia di amministrazione di Microsoft 365 non sia lo strumento migliore.</span><span class="sxs-lookup"><span data-stu-id="10332-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="10332-200">Ad esempio, si supponga di dover cambiare il prefisso su migliaia di numeri di telefono o di rimuovere l'utente specifico *Ken* resite da tutti i siti di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="10332-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="10332-201">Come è possibile eseguire questa operazione nell'interfaccia di amministrazione di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="10332-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="10332-202">Per l'ultimo esempio, si supponga che siano disponibili diverse centinaia di siti di SharePoint Online e che non si conoscano quelli di cui è membro Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="10332-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="10332-203">È necessario avviare l'interfaccia di amministrazione di Microsoft 365 e quindi eseguire questa procedura per ogni sito:</span><span class="sxs-lookup"><span data-stu-id="10332-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="10332-204">Selezionare l' **URL** del sito.</span><span class="sxs-lookup"><span data-stu-id="10332-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="10332-205">Nella casella **Proprietà raccolta siti** selezionare il collegamento **Indirizzo sito Web** per aprire il sito.</span><span class="sxs-lookup"><span data-stu-id="10332-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="10332-206">Nel sito selezionare **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="10332-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="10332-207">Nella finestra di dialogo **Condividi** , selezionare il collegamento che consente di visualizzare tutti gli utenti che dispongono delle autorizzazioni per il sito:</span><span class="sxs-lookup"><span data-stu-id="10332-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Esempio di visualizzazione di membri del sito SharePoint Online nell'interfaccia di amministrazione di SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="10332-209">Nella finestra **di dialogo condiviso con** selezionare **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="10332-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="10332-210">Scorrere l'elenco degli utenti, trovare e selezionare Ken (supponendo che disponga delle autorizzazioni per il sito) e quindi selezionare **Rimuovi autorizzazioni utente**.</span><span class="sxs-lookup"><span data-stu-id="10332-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="10332-211">Questo richiederebbe *molto* tempo per diverse centinaia di siti.</span><span class="sxs-lookup"><span data-stu-id="10332-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="10332-212">L'alternativa consiste nell'eseguire il seguente comando in PowerShell per Microsoft 365 per rimuovere Ken remario da tutti i siti:</span><span class="sxs-lookup"><span data-stu-id="10332-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="10332-213">Questo comando richiede l'installazione del [modulo di PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="10332-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="10332-214">L'interpretazione di questo comando di PowerShell è: recuperare tutti i siti di SharePoint nella sottoscrizione Microsoft 365 corrente (**Get-SPOSite**) e per ogni sito rimuovere Ken Meyer dall'elenco degli utenti che possono accedervi (**foreach {Remove-consorter-site $ \_ . URL-LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="10332-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="10332-215">Diciamo a Microsoft 365 di rimuovere Ken Meyer da ogni sito, compresi quelli a cui non ha accesso.</span><span class="sxs-lookup"><span data-stu-id="10332-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="10332-216">In questo modo, i risultati visualizzeranno gli errori per i siti a cui non è consentito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="10332-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="10332-217">È possibile utilizzare una condizione aggiuntiva su questo comando per rimuovere Ken Meyer solo dai siti che lo dispongono nell'elenco di accesso.</span><span class="sxs-lookup"><span data-stu-id="10332-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="10332-218">Tuttavia, gli errori restituiti non causano danni per i siti stessi.</span><span class="sxs-lookup"><span data-stu-id="10332-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="10332-219">Questo comando potrebbe richiedere alcuni minuti per l'esecuzione in centinaia di siti anziché ore di utilizzo dell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="10332-220">Di seguito è riportato un altro esempio di operazione in blocco.</span><span class="sxs-lookup"><span data-stu-id="10332-220">Here's another bulk operation example.</span></span> <span data-ttu-id="10332-221">Utilizzare questo comando per aggiungere *Bonnie Kearney*, un nuovo amministratore di SharePoint, a tutti i siti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="10332-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="10332-222">L'interpretazione di questo comando di PowerShell è: recuperare tutti i siti di SharePoint nella sottoscrizione Microsoft 365 corrente e per ogni sito consentire a Bonnie Kearney Access aggiungendo il nome di accesso al gruppo membri del sito (**foreach {Add-Consorter-site $ \_ . URL-LoginName "bkearney \@ litwareinc.com"-gruppo "membri"}**).</span><span class="sxs-lookup"><span data-stu-id="10332-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="10332-223">PowerShell per Microsoft 365 è ottimo per filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="10332-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="10332-224">L'interfaccia di amministrazione di Microsoft 365 offre diversi modi per filtrare i dati in modo da individuare facilmente un sottoinsieme di informazioni mirato.</span><span class="sxs-lookup"><span data-stu-id="10332-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="10332-225">Ad esempio, Exchange facilita il filtro di qualsiasi proprietà relativa alla cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="10332-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="10332-226">Ad esempio, di seguito è riportato l'elenco delle cassette postali per tutti gli utenti che vivono nella città di Bloomington:</span><span class="sxs-lookup"><span data-stu-id="10332-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Esempio di ricerca avanzata nell'interfaccia di amministrazione di Microsoft 365 per l'elenco delle cassette postali per tutti gli utenti che vivono nella città di Bloomington.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="10332-228">L'interfaccia di amministrazione di Exchange consente di combinare i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="10332-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="10332-229">Ad esempio, è possibile trovare le cassette postali per tutte le persone che vivono in Bloomington e lavorano nel reparto Finanza.</span><span class="sxs-lookup"><span data-stu-id="10332-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="10332-230">Tuttavia, è possibile eseguire limitazioni nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="10332-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="10332-231">Ad esempio, non è possibile trovare facilmente le cassette postali di persone che vivono in Bloomington *o* San Diego o le cassette postali per tutte le persone che non vivono in Bloomington.</span><span class="sxs-lookup"><span data-stu-id="10332-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="10332-232">Per ottenere un elenco delle cassette postali per tutte le persone che vivono in Bloomington o San Diego, è possibile utilizzare il seguente comando di PowerShell per Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="10332-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="10332-233">Di seguito è riportato un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="10332-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="10332-234">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nell'attuale sottoscrizione di Microsoft 365 che dispongono di una cassetta postale nella città di San Diego o Bloomington (**dove {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-and ($ \_ . City-EQ "San Diego"-oppure $ \_ . City-EQ "Bloomington")}**), quindi visualizzare il nome e la città per ognuno (**selezionare DisplayName, City**).</span><span class="sxs-lookup"><span data-stu-id="10332-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="10332-235">Ed ecco il comando per elencare tutte le cassette postali per le persone che vivono ovunque tranne Bloomington:</span><span class="sxs-lookup"><span data-stu-id="10332-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="10332-236">Di seguito è riportato un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="10332-236">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

<span data-ttu-id="10332-237">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nell'attuale sottoscrizione di Microsoft 365 che dispongono di una cassetta postale che non si trova nella città di Bloomington (**dove {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-e $ \_ . City-ne "Bloomington"}**), quindi visualizzare il nome e la città per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="10332-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="10332-238">Utilizzo di caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="10332-238">Use wildcards</span></span>

<span data-ttu-id="10332-239">È inoltre possibile utilizzare i caratteri jolly nei filtri di PowerShell per far corrispondere parte di un nome.</span><span class="sxs-lookup"><span data-stu-id="10332-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="10332-240">Ad esempio, si supponga di essere alla ricerca di un account utente.</span><span class="sxs-lookup"><span data-stu-id="10332-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="10332-241">Tutto quello che è possibile ricordare è che il cognome dell'utente era *Anderson* o forse *Henderson* o *Jorgenson*.</span><span class="sxs-lookup"><span data-stu-id="10332-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="10332-242">È possibile rintracciare l'utente nell'interfaccia di amministrazione di Microsoft 365 utilizzando lo strumento di ricerca ed effettuando tre ricerche diverse:</span><span class="sxs-lookup"><span data-stu-id="10332-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="10332-243">Una per  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="10332-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="10332-244">Una per  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="10332-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="10332-245">Una per  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="10332-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="10332-246">Poiché tutti e tre questi nomi terminano con "son", è possibile indicare a PowerShell di visualizzare tutti gli utenti il cui nome termina con "son".</span><span class="sxs-lookup"><span data-stu-id="10332-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="10332-247">Di seguito è riportato il comando:</span><span class="sxs-lookup"><span data-stu-id="10332-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="10332-248">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente, ma utilizzare un filtro che elenca solo gli utenti i cui cognomi terminano con "son" (**-Filter ' {LastName-like " \* son"}'**).</span><span class="sxs-lookup"><span data-stu-id="10332-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="10332-249">Lo \* stand per qualsiasi set di caratteri, ovvero lettere nel cognome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="10332-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="10332-250">PowerShell per Microsoft 365 rende più semplice la stampa o il salvataggio dei dati</span><span class="sxs-lookup"><span data-stu-id="10332-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="10332-251">L'interfaccia di amministrazione di Microsoft 365 consente di visualizzare gli elenchi di dati.</span><span class="sxs-lookup"><span data-stu-id="10332-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="10332-252">Di seguito è riportato un esempio dell'interfaccia di amministrazione di Skype for business online in cui viene visualizzato un elenco di utenti abilitati per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="10332-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Esempio di interfaccia di amministrazione di Skype for Business online che mostra un elenco di utenti abilitati a Skype for Business online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="10332-254">Per salvare tali informazioni in un file, è necessario incollarlo in un foglio di lavoro di documento o di Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="10332-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="10332-255">In entrambi i casi potrebbe essere necessaria una formattazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="10332-255">Either case might require additional formatting.</span></span> <span data-ttu-id="10332-256">Inoltre, l'interfaccia di amministrazione di Microsoft 365 non consente di stampare direttamente l'elenco visualizzato.</span><span class="sxs-lookup"><span data-stu-id="10332-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="10332-257">Fortunatamente, è possibile utilizzare PowerShell per non solo visualizzare l'elenco ma per salvarlo in un file che può essere importato facilmente in Excel.</span><span class="sxs-lookup"><span data-stu-id="10332-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="10332-258">Di seguito è riportato un comando di esempio per salvare i dati degli utenti di Skype for business online in un file con valori delimitati da virgole (CSV), che può essere importato facilmente come tabella in un foglio di lavoro di Excel:</span><span class="sxs-lookup"><span data-stu-id="10332-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="10332-259">Di seguito è riportato un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="10332-259">Here's an example of the results:</span></span>
  
![Esempio di una tabella importata in un foglio di lavoro di Excel per i dati degli utenti di Skype for business online salvati in un file con valori delimitati da virgole.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="10332-261">L'interpretazione di questo comando di PowerShell è: ottenere tutti gli utenti di Skype for business online nella sottoscrizione Microsoft 365 corrente (**Get-CsOnlineUser**); ottenere solo il nome utente, l'UPN e la posizione (**selezionare DisplayName, userPrincipalName, UsageLocation**); e quindi salvare le informazioni in un file CSV denominato C: \\ logs \\SfBUsers.csv (**Export-CSV-path "c: \\ logs \\SfBUsers.csv"-NoTypeInformation**).</span><span class="sxs-lookup"><span data-stu-id="10332-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="10332-262">È inoltre possibile utilizzare le opzioni per salvare questo elenco come un file XML o una pagina HTML.</span><span class="sxs-lookup"><span data-stu-id="10332-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="10332-263">Infatti, con ulteriori comandi di PowerShell, è possibile salvarlo direttamente come file di Excel, con qualsiasi formattazione personalizzata desiderata.</span><span class="sxs-lookup"><span data-stu-id="10332-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="10332-264">È anche possibile inviare l'output di un comando di PowerShell che consente di visualizzare un elenco direttamente alla stampante predefinita in Windows.</span><span class="sxs-lookup"><span data-stu-id="10332-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="10332-265">Di seguito è riportato un comando di esempio:</span><span class="sxs-lookup"><span data-stu-id="10332-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="10332-266">Di seguito, è riportato l'aspetto del documento stampato:</span><span class="sxs-lookup"><span data-stu-id="10332-266">Here's what your printed document will look like:</span></span>
  
![Esempio di un documento stampato che è stato l'output di un comando di PowerShell inviato direttamente alla stampante predefinita in Windows.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="10332-268">L'interpretazione di questo comando di PowerShell è: ottenere tutti gli utenti di Skype for business online nella sottoscrizione Microsoft 365 corrente; ottenere solo il nome utente, l'UPN e la posizione. e quindi invia queste informazioni alla stampante predefinita di Windows (**fuori stampante**).</span><span class="sxs-lookup"><span data-stu-id="10332-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="10332-269">Il documento stampato ha la stessa formattazione semplice della visualizzazione nella finestra di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10332-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="10332-270">Per ottenere una copia cartacea, è sufficiente aggiungere **| Out-Printer** alla fine del comando.</span><span class="sxs-lookup"><span data-stu-id="10332-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="10332-271">PowerShell per Microsoft 365 consente di gestire diversi prodotti server</span><span class="sxs-lookup"><span data-stu-id="10332-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="10332-272">I componenti che compongono Microsoft 365 sono stati concepiti per funzionare insieme.</span><span class="sxs-lookup"><span data-stu-id="10332-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="10332-273">Si supponga, ad esempio, di aggiungere un nuovo utente a Microsoft 365 e di specificare tali informazioni come reparto e numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="10332-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="10332-274">Tali informazioni saranno quindi disponibili se si accede alle informazioni dell'utente in uno dei servizi Microsoft 365: Skype for business online, Exchange o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="10332-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="10332-275">Si tratta di informazioni generali che interessano la famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="10332-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="10332-276">Le informazioni specifiche del prodotto, ad esempio le informazioni relative alla cassetta postale di Exchange di un utente, non sono in genere disponibili in tutta la famiglia.</span><span class="sxs-lookup"><span data-stu-id="10332-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="10332-277">Ad esempio, le informazioni sull'abilitazione o meno della cassetta postale di un utente sono disponibili solo nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="10332-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="10332-278">Si supponga di voler creare un report che mostra le seguenti informazioni per tutti gli utenti:</span><span class="sxs-lookup"><span data-stu-id="10332-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="10332-279">Nome visualizzato dell'utente</span><span class="sxs-lookup"><span data-stu-id="10332-279">The user's display name</span></span>
    
- <span data-ttu-id="10332-280">Se l'utente ha una licenza per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10332-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="10332-281">L'abilitazione della cassetta postale di Exchange dell'utente.</span><span class="sxs-lookup"><span data-stu-id="10332-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="10332-282">L'abilitazione per Skype for Business online dell'utente</span><span class="sxs-lookup"><span data-stu-id="10332-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="10332-283">Non è possibile produrre facilmente un rapporto di questo tipo nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10332-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="10332-284">In alternativa, è necessario creare un documento distinto per archiviare le informazioni, ad esempio un foglio di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="10332-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="10332-285">Ottenere quindi tutti i nomi utente e le informazioni di licenza dall'interfaccia di amministrazione di Microsoft 365, ottenere informazioni sulla cassetta postale dall'interfaccia di amministrazione di Exchange, ottenere informazioni su Skype for business online dall'interfaccia di amministrazione di Skype for business online e quindi combinare tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="10332-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="10332-286">L'alternativa consiste nell'usare uno script di PowerShell per compilare il report.</span><span class="sxs-lookup"><span data-stu-id="10332-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="10332-287">Lo script di esempio seguente è più complesso rispetto ai comandi visualizzati finora in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="10332-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="10332-288">Tuttavia, dimostra la possibilità di utilizzare PowerShell per creare visualizzazioni di informazioni difficilmente ottenibili in altro modo.</span><span class="sxs-lookup"><span data-stu-id="10332-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="10332-289">Ecco lo script per compilare e visualizzare l'elenco di cui hai bisogno:</span><span class="sxs-lookup"><span data-stu-id="10332-289">Here's the script to compile and display the list you need:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="10332-290">Di seguito è riportato un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="10332-290">Here's an example of the results:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="10332-291">L'interpretazione di questo script di PowerShell è la seguente:</span><span class="sxs-lookup"><span data-stu-id="10332-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="10332-292">Ottenere tutti gli utenti nella sottoscrizione Microsoft 365 corrente e archiviare le informazioni in una variabile denominata *$x* (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="10332-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="10332-293">Avviare un ciclo che viene eseguito su tutti gli utenti nella variabile $x (**foreach ($i in $x)**).</span><span class="sxs-lookup"><span data-stu-id="10332-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="10332-294">Definire una variabile denominata *$y* e archiviarvi le informazioni sulla cassetta postale dell'utente (**$y = Get-Mailbox-Identity $i. userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="10332-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="10332-295">Aggiungere una nuova proprietà alle informazioni utente denominate *IsMailBoxEnabled*.</span><span class="sxs-lookup"><span data-stu-id="10332-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="10332-296">Impostarla sul valore della proprietà IsMailBoxEnabled della cassetta postale dell'utente (**$i | Add-Member-MemberType NoteProperty-Name IsMailBoxEnabled-value $y. IsMailBoxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="10332-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="10332-297">Definire una variabile denominata *$y*e archiviare le informazioni di Skype for business online dell'utente (**$y = Get-CsOnlineUser-Identity $i. userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="10332-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="10332-298">Aggiungere una nuova proprietà alle informazioni utente denominate *EnabledForSfB*.</span><span class="sxs-lookup"><span data-stu-id="10332-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="10332-299">Impostarla sul valore della proprietà Enabled delle informazioni di Skype for business online dell'utente (**$i | Add-Member-MemberType NoteProperty-Name EnabledForSfB-value $y. Enabled**).</span><span class="sxs-lookup"><span data-stu-id="10332-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="10332-300">Visualizzare l'elenco degli utenti, ma includere solo il nome, se sono concessi in licenza, e le due nuove proprietà che indicano se la propria cassetta postale è abilitata e se sono abilitati per Skype for business online (**$x | Selezionare DisplayName, con licenza, IsMailboxEnabled, EnabledforSfB**).</span><span class="sxs-lookup"><span data-stu-id="10332-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="10332-301">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10332-301">See also</span></span>

[<span data-ttu-id="10332-302">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10332-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="10332-303">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="10332-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="10332-304">Usare Windows PowerShell per creare report in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10332-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
