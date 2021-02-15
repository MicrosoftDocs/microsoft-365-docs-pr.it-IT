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
description: 'Riepilogo: comprendere perché è necessario usare PowerShell per gestire Microsoft 365, in alcuni casi in modo più efficiente e in altri casi per necessità.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754107"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="3d214-103">Perché è necessario usare PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d214-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="3d214-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="3d214-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3d214-105">Con l'interfaccia di amministrazione di Microsoft 365, è possibile gestire gli account utente e le licenze di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="3d214-106">È inoltre possibile gestire i servizi di Microsoft 365, ad esempio Exchange Online, Teams e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3d214-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="3d214-107">Se invece si utilizza PowerShell per gestire questi servizi, è possibile e sfruttare l'ambiente della riga di comando e del linguaggio di scripting per velocità, automazione e funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="3d214-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="3d214-108">Questo articolo illustra come usare PowerShell per gestire Microsoft 365 per:</span><span class="sxs-lookup"><span data-stu-id="3d214-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="3d214-109">Visualizzare informazioni aggiuntive che non è possibile visualizzare nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d214-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="3d214-110">Configurare le funzionalità e le impostazioni solo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d214-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="3d214-111">Eseguire operazioni in blocco</span><span class="sxs-lookup"><span data-stu-id="3d214-111">Do bulk operations</span></span>
    
- <span data-ttu-id="3d214-112">Filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="3d214-112">Filter data</span></span>
    
- <span data-ttu-id="3d214-113">Stampare o salvare dati</span><span class="sxs-lookup"><span data-stu-id="3d214-113">Print or save data</span></span>
    
- <span data-ttu-id="3d214-114">Gestire tra i servizi</span><span class="sxs-lookup"><span data-stu-id="3d214-114">Manage across services</span></span>
    
<span data-ttu-id="3d214-115">Tenere presente che PowerShell per Microsoft 365 è un set di moduli per Windows PowerShell, ovvero un ambiente da riga di comando per i servizi e le piattaforme basati su Windows.</span><span class="sxs-lookup"><span data-stu-id="3d214-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="3d214-116">Questo ambiente crea un linguaggio della shell dei comandi che può essere esteso con moduli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="3d214-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="3d214-117">Consente di eseguire comandi o script semplici o complessi.</span><span class="sxs-lookup"><span data-stu-id="3d214-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="3d214-118">Ad esempio, dopo aver installato i moduli di PowerShell per Microsoft 365 e aver eseguito la connessione all'abbonamento a Microsoft 365, è possibile eseguire il comando seguente per elencare tutte le cassette postali degli utenti per Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="3d214-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="3d214-119">È anche possibile ottenere l'elenco delle cassette postali utilizzando l'interfaccia di amministrazione di Microsoft 365, ma il conteggio degli elementi in tutti gli elenchi per tutti i siti per tutte le app Web non è semplice.</span><span class="sxs-lookup"><span data-stu-id="3d214-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="3d214-120">PowerShell per Microsoft 365 è progettato per facilitare la gestione di Microsoft 365, non per sostituire l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="3d214-121">Gli amministratori devono essere in grado di usare PowerShell per Microsoft 365 perché alcune procedure di configurazione possono essere eseguite solo tramite i comandi di PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="3d214-122">In questi casi, è necessario sapere come:</span><span class="sxs-lookup"><span data-stu-id="3d214-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="3d214-123">Installare i moduli di PowerShell per Microsoft 365 (operazione eseguita una sola volta per ogni computer amministratore).</span><span class="sxs-lookup"><span data-stu-id="3d214-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="3d214-124">Connettersi all'abbonamento a Microsoft 365 (una volta per ogni sessione di PowerShell).</span><span class="sxs-lookup"><span data-stu-id="3d214-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="3d214-125">Raccogliere le informazioni necessarie per eseguire i comandi di PowerShell necessari per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="3d214-126">Eseguire i comandi di PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="3d214-127">Dopo aver appreso queste competenze di base, non è necessario elencare gli utenti delle cassette postali utilizzando il **comando Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="3d214-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="3d214-128">Inoltre, non è necessario comprendere come creare un nuovo comando come il comando menzionato in precedenza per contare tutti gli elementi in tutti gli elenchi per tutti i siti per tutte le app Web.</span><span class="sxs-lookup"><span data-stu-id="3d214-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="3d214-129">Microsoft e la community di amministratori possono aiutarti a eseguire tali attività in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3d214-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="3d214-130">PowerShell per Microsoft 365 può rivelare informazioni che non è possibile visualizzare con l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d214-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="3d214-131">L'interfaccia di amministrazione di Microsoft 365 visualizza molte informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="3d214-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="3d214-132">Tuttavia, non vengono visualizzate tutte le informazioni possibili archiviate da Microsoft 365 su utenti, licenze, cassette postali e siti.</span><span class="sxs-lookup"><span data-stu-id="3d214-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="3d214-133">Ecco un esempio per utenti e *gruppi nell'interfaccia* di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="3d214-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Esempio di visualizzazione di utenti e gruppi nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="3d214-135">Questa visualizzazione fornisce le informazioni necessarie in molti casi.</span><span class="sxs-lookup"><span data-stu-id="3d214-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="3d214-136">Tuttavia, in alcuni casi sono necessarie informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="3d214-136">However, there are times when you need more.</span></span> <span data-ttu-id="3d214-137">Ad esempio, le licenze di Microsoft 365 (e le funzionalità di Microsoft 365 disponibili per un utente) dipendono in parte dalla posizione geografica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="3d214-138">I criteri e le funzionalità che è possibile estendere a un utente che risiede negli Stati Uniti potrebbero non essere uguali a quelli che è possibile estendere a un utente in India o Belgio.</span><span class="sxs-lookup"><span data-stu-id="3d214-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="3d214-139">Seguire questi passaggi nell'interfaccia di amministrazione di Microsoft 365 per determinare la posizione geografica di un utente:</span><span class="sxs-lookup"><span data-stu-id="3d214-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="3d214-140">Fare doppio clic sul **Nome visualizzato** dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="3d214-141">Nel riquadro di visualizzazione delle proprietà dell'utente selezionare **i dettagli.**</span><span class="sxs-lookup"><span data-stu-id="3d214-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="3d214-142">Nella visualizzazione dei dettagli, selezionare **ulteriori dettagli.**</span><span class="sxs-lookup"><span data-stu-id="3d214-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="3d214-143">Scorrere fino a trovare l'intestazione **Paese o area geografica:**</span><span class="sxs-lookup"><span data-stu-id="3d214-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Esempio di informazioni sull'area geografica per un utente nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="3d214-145">Prendere nota del nome visualizzato e della posizione dell'utente su un pezzo di carta o copiarlo e incollarlo nel Blocco note.</span><span class="sxs-lookup"><span data-stu-id="3d214-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="3d214-146">È necessario ripetere questa procedura per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="3d214-147">Se sono molti gli utenti, questo processo può essere noioso.</span><span class="sxs-lookup"><span data-stu-id="3d214-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="3d214-148">Con PowerShell per Microsoft 365, è possibile visualizzare queste informazioni per tutti gli utenti usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3d214-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="3d214-149">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* nel nome.</span><span class="sxs-lookup"><span data-stu-id="3d214-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="3d214-150">È necessario eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d214-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="3d214-151">Ecco un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="3d214-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="3d214-152">L'interpretazione di questo comando di PowerShell è: Ottenere tutti gli utenti nella sottoscrizione di Microsoft 365 corrente (**Get-AzureADUser**), ma visualizzare solo il nome e il percorso di ogni utente (**Selezionare DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="3d214-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="3d214-153">Poiché PowerShell per Microsoft 365 supporta un linguaggio della shell dei comandi, è possibile modificare ulteriormente le informazioni ottenute dal **comando Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="3d214-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="3d214-154">Ad esempio, si potrebbe desiderare di ordinare questi utenti in base alla loro posizione, raggruppando tutti gli utenti brasiliani, tutti gli utenti degli Stati Uniti e così via.</span><span class="sxs-lookup"><span data-stu-id="3d214-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="3d214-155">Ecco il comando:</span><span class="sxs-lookup"><span data-stu-id="3d214-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="3d214-156">Ecco un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="3d214-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="3d214-157">L'interpretazione di questo comando di PowerShell è: Ottenere tutti gli utenti nella sottoscrizione di Microsoft 365 corrente, ma visualizzare solo il nome e il percorso di ogni utente e ordinarli prima in base alla posizione e quindi al nome (**Sort UsageLocation, DisplayName**).</span><span class="sxs-lookup"><span data-stu-id="3d214-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="3d214-158">È inoltre possibile utilizzare filtri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="3d214-158">You can also use additional filtering.</span></span> <span data-ttu-id="3d214-159">Ad esempio, se si desidera visualizzare tali informazioni sugli utenti residenti in Brasile, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="3d214-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="3d214-160">Ecco un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="3d214-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="3d214-161">L'interpretazione di questo comando di PowerShell è: Ottenere tutti gli utenti nella sottoscrizione di Microsoft 365 corrente la cui posizione è il Brasile (**Where {$ \_ . UsageLocation -eq "BR"}**) e quindi visualizzare il nome e la posizione di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="3d214-162">**Nota sui domini di grandi dimensioni**</span><span class="sxs-lookup"><span data-stu-id="3d214-162">**A note about large domains**</span></span>
  
<span data-ttu-id="3d214-163">Se si dispone di un dominio di grandi dimensioni con decine di migliaia di utenti, provare alcuni degli esempi mostrati in questo articolo potrebbe causare limitazioni.</span><span class="sxs-lookup"><span data-stu-id="3d214-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="3d214-164">In base a fattori come la potenza di elaborazione e la larghezza di banda di rete disponibile, è possibile che si stia tentando di eseguire troppe attività contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3d214-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="3d214-165">Le organizzazioni di grandi dimensioni potrebbero voler dividere alcune di queste operazioni di PowerShell in due comandi.</span><span class="sxs-lookup"><span data-stu-id="3d214-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="3d214-166">Ad esempio, il comando seguente restituisce tutti gli account utente e mostra il nome e il percorso di ognuno:</span><span class="sxs-lookup"><span data-stu-id="3d214-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="3d214-167">Questa operazione funziona perfettamente per i domini più piccoli.</span><span class="sxs-lookup"><span data-stu-id="3d214-167">That works great for smaller domains.</span></span> <span data-ttu-id="3d214-168">In un'organizzazione di grandi dimensioni, tuttavia, è possibile suddividere l'operazione in due comandi: un comando per archiviare le informazioni sull'account utente in una variabile e un altro per visualizzare le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="3d214-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="3d214-169">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="3d214-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="3d214-170">L'interpretazione di questo set di comandi di PowerShell è:</span><span class="sxs-lookup"><span data-stu-id="3d214-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="3d214-171">Ottenere tutti gli utenti nell'abbonamento a Microsoft 365 corrente e archiviare le informazioni in una variabile denominata $x (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="3d214-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="3d214-172">Visualizzare il contenuto della variabile *$x*, ma includere solo il nome e la posizione di ogni utente (**$x | Selezionare DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="3d214-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="3d214-173">Microsoft 365 include funzionalità che è possibile configurare solo con PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d214-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="3d214-174">L'interfaccia di amministrazione di Microsoft 365 ha lo scopo di fornire l'accesso alle attività amministrative comuni e utili che si applicano alla maggior parte degli ambienti.</span><span class="sxs-lookup"><span data-stu-id="3d214-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="3d214-175">In altre parole, l'interfaccia di amministrazione di Microsoft 365 è stata progettata in modo che l'amministratore tipico possa eseguire le attività di gestione più comuni.</span><span class="sxs-lookup"><span data-stu-id="3d214-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="3d214-176">Tuttavia, alcune attività non possono essere eseguite nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="3d214-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="3d214-177">Ad esempio, l'interfaccia di amministrazione di Skype for Business online offre alcune opzioni per la creazione di inviti alle riunioni personalizzati:</span><span class="sxs-lookup"><span data-stu-id="3d214-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Esempio di visualizzazione di inviti personalizzati a riunioni nell’interfaccia di amministrazione di Skype for Business online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="3d214-179">Con queste impostazioni, è possibile aggiungere un tocco di personalizzazione e professionalità alle convocazioni di riunioni.</span><span class="sxs-lookup"><span data-stu-id="3d214-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="3d214-180">Tuttavia, le impostazioni di configurazione delle riunioni sono più diverse dalla semplice creazione di inviti alle riunioni personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3d214-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="3d214-181">Ad esempio, per impostazione predefinita le riunioni consentono:</span><span class="sxs-lookup"><span data-stu-id="3d214-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="3d214-182">A utenti anonimi di ottenere l'ingresso automatico a ogni riunione.</span><span class="sxs-lookup"><span data-stu-id="3d214-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="3d214-183">Ai partecipanti di registrare una riunione.</span><span class="sxs-lookup"><span data-stu-id="3d214-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="3d214-184">A tutti gli utenti dell'organizzazione di essere designati come relatori quando partecipano a riunione.</span><span class="sxs-lookup"><span data-stu-id="3d214-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="3d214-185">Queste impostazioni non sono disponibili dall'interfaccia di amministrazione di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3d214-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="3d214-186">È possibile controllarli da PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="3d214-187">Ecco un comando che disabilita queste tre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="3d214-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="3d214-188">Per eseguire questo comando, è necessario installare il modulo [PowerShell di Skype for Business online. ](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="3d214-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="3d214-189">L'interpretazione di questo comando di PowerShell è:</span><span class="sxs-lookup"><span data-stu-id="3d214-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="3d214-190">Nelle impostazioni per le nuove riunioni di Skype for Business online (**Set-CsMeetingConfiguration**), disabilitare l'accesso automatico agli utenti anonimi alle riunioni (**-AdmitAnonymousUsersByDefault $False**).</span><span class="sxs-lookup"><span data-stu-id="3d214-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="3d214-191">Disabilitare la possibilità per i partecipanti di registrare le riunioni (**-AllowConferenceRecording $False**).</span><span class="sxs-lookup"><span data-stu-id="3d214-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="3d214-192">Non designare tutti gli utenti dell'organizzazione come relatori (**-DesignateAsPresenter "None"**).</span><span class="sxs-lookup"><span data-stu-id="3d214-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="3d214-193">Per ripristinare queste impostazioni predefinite (abilitare le opzioni), eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="3d214-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="3d214-194">Esistono anche altri scenari simili, motivo per cui gli amministratori devono sapere come eseguire i comandi di PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="3d214-195">PowerShell per Microsoft 365 è ideale per le operazioni in blocco</span><span class="sxs-lookup"><span data-stu-id="3d214-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="3d214-196">Le interfacce visive come l'interfaccia di amministrazione di Microsoft 365 sono particolarmente utili quando è necessario eseguire un'unica operazione.</span><span class="sxs-lookup"><span data-stu-id="3d214-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="3d214-197">Ad esempio, se è necessario disabilitare un account utente, è possibile utilizzare l'interfaccia di amministrazione per individuare e deselezionare rapidamente una casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="3d214-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="3d214-198">Questa operazione può essere più semplice rispetto all'esecuzione di un'operazione simile in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d214-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="3d214-199">Tuttavia, se è necessario modificare molti elementi o alcuni elementi selezionati in un ampio set di altri elementi, l'interfaccia di amministrazione di Microsoft 365 potrebbe non essere lo strumento migliore.</span><span class="sxs-lookup"><span data-stu-id="3d214-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="3d214-200">Si supponga ad esempio che sia necessario modificare il prefisso su migliaia di numeri di telefono o rimuovere l'utente *specifico Ken Myer* da tutti i siti di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3d214-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="3d214-201">Come eseguire questa operazione nell'interfaccia di amministrazione di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="3d214-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="3d214-202">Nell'ultimo esempio si supponga di avere diverse centinaia di siti di SharePoint Online e di non sapere di quali siti è membro Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="3d214-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="3d214-203">È necessario iniziare dall'interfaccia di amministrazione di Microsoft 365 e quindi eseguire questa procedura per ogni sito:</span><span class="sxs-lookup"><span data-stu-id="3d214-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="3d214-204">Selezionare **l'URL** del sito.</span><span class="sxs-lookup"><span data-stu-id="3d214-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="3d214-205">Nella casella **delle proprietà della raccolta** siti selezionare il collegamento Indirizzo sito **Web** per aprire il sito.</span><span class="sxs-lookup"><span data-stu-id="3d214-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="3d214-206">Nel sito selezionare **Condividi.**</span><span class="sxs-lookup"><span data-stu-id="3d214-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="3d214-207">Nella finestra **di** dialogo Condividi selezionare il collegamento che mostra tutti gli utenti che dispongono delle autorizzazioni per il sito:</span><span class="sxs-lookup"><span data-stu-id="3d214-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Esempio di visualizzazione di membri del sito SharePoint Online nell'interfaccia di amministrazione di SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="3d214-209">Nella finestra **di dialogo** Condivisi con selezionare **Avanzate.**</span><span class="sxs-lookup"><span data-stu-id="3d214-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="3d214-210">Scorrere l'elenco degli utenti verso il basso, trovare e selezionare Ken Myer (presupponendo che abbia le autorizzazioni per il sito), quindi selezionare **Rimuovi autorizzazioni utente.**</span><span class="sxs-lookup"><span data-stu-id="3d214-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="3d214-211">Questa operazione potrebbe richiedere *molto tempo* per diverse centinaia di siti.</span><span class="sxs-lookup"><span data-stu-id="3d214-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="3d214-212">L'alternativa consiste nell'eseguire il comando seguente in PowerShell per Microsoft 365 per rimuovere Ken Myer da tutti i siti:</span><span class="sxs-lookup"><span data-stu-id="3d214-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="3d214-213">Questo comando richiede l'installazione del modulo [PowerShell di SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="3d214-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="3d214-214">L'interpretazione di questo comando di PowerShell è: Ottenere tutti i siti di SharePoint nella sottoscrizione di Microsoft 365 corrente (**Get-SPOSite**) e per ogni sito rimuovere Ken Meyer dall'elenco degli utenti che possono accedervi (**ForEach {Remove-SPOUser -Site $ \_ . Url -LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="3d214-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="3d214-215">Microsoft 365 deve rimuovere Ken Meyer da ogni sito, inclusi quelli a cui non ha accesso.</span><span class="sxs-lookup"><span data-stu-id="3d214-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="3d214-216">I risultati mostreranno quindi gli errori per i siti a cui non ha accesso.</span><span class="sxs-lookup"><span data-stu-id="3d214-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="3d214-217">È possibile utilizzare una condizione aggiuntiva per questo comando per rimuovere Ken Meyer solo dai siti che lo hanno nell'elenco di accesso.</span><span class="sxs-lookup"><span data-stu-id="3d214-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="3d214-218">Tuttavia, gli errori restituiti non causano alcun danno ai siti stessi.</span><span class="sxs-lookup"><span data-stu-id="3d214-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="3d214-219">Questo comando potrebbe richiedere alcuni minuti per essere eseguito su centinaia di siti, anziché ore di lavoro tramite l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="3d214-220">Ecco un altro esempio di operazione in blocco.</span><span class="sxs-lookup"><span data-stu-id="3d214-220">Here's another bulk operation example.</span></span> <span data-ttu-id="3d214-221">Utilizzare questo comando per aggiungere *Bonnie Kearney,* un nuovo amministratore di SharePoint, a tutti i siti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="3d214-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="3d214-222">L'interpretazione di questo comando di PowerShell è: Ottenere tutti i siti di SharePoint nella sottoscrizione di Microsoft 365 corrente e per ogni sito consentire l'accesso a Bonnie Kearney aggiungendo il suo nome di accesso al gruppo Membri del sito (**ForEach {Add-SPOUser -Site $ \_ . Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).</span><span class="sxs-lookup"><span data-stu-id="3d214-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="3d214-223">PowerShell per Microsoft 365 è ideale per filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="3d214-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="3d214-224">L'interfaccia di amministrazione di Microsoft 365 offre diversi modi per filtrare i dati per individuare facilmente un sottoinsieme di informazioni mirato.</span><span class="sxs-lookup"><span data-stu-id="3d214-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="3d214-225">Ad esempio, Exchange facilita il filtro di qualsiasi proprietà relativa alla cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="3d214-226">Ad esempio, ecco l'elenco delle cassette postali per tutti gli utenti che vivono nella città di Bloomington:</span><span class="sxs-lookup"><span data-stu-id="3d214-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Esempio di ricerca avanzata nell'interfaccia di amministrazione di Microsoft 365 per l'elenco delle cassette postali per tutti gli utenti che vivono nella città di Bloomington.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="3d214-228">L'interfaccia di amministrazione di Exchange consente di combinare i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="3d214-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="3d214-229">Ad esempio, è possibile trovare le cassette postali per tutte le persone che vivono a Bloomington e lavorano nel reparto Finance.</span><span class="sxs-lookup"><span data-stu-id="3d214-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="3d214-230">Tuttavia, esistono limitazioni per le attività che è possibile eseguire nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3d214-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="3d214-231">Ad esempio, non è possibile trovare facilmente le cassette postali delle persone che vivono a *Bloomington* o San Diego o le cassette postali di tutte le persone che non vivono a Bloomington.</span><span class="sxs-lookup"><span data-stu-id="3d214-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="3d214-232">È possibile utilizzare il seguente comando di PowerShell per Microsoft 365 per ottenere un elenco di cassette postali per tutte le persone che vivono a Bloomington o San Diego:</span><span class="sxs-lookup"><span data-stu-id="3d214-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="3d214-233">Ecco un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="3d214-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="3d214-234">L'interpretazione di questo comando di PowerShell è: Ottenere tutti gli utenti nell'abbonamento a Microsoft 365 corrente che dispongono di una cassetta postale nella città di San Diego o Bloomington (**Where {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and ($ \_ . City -eq "San Diego" -or $ \_ . City -eq "Bloomington")}**), quindi visualizzare il nome e la città per ognuno (**Select DisplayName, City**).</span><span class="sxs-lookup"><span data-stu-id="3d214-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="3d214-235">Ed ecco il comando per elencare tutte le cassette postali per le persone che vivono ovunque tranne Bloomington:</span><span class="sxs-lookup"><span data-stu-id="3d214-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="3d214-236">Ecco un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="3d214-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="3d214-237">L'interpretazione di questo comando di PowerShell è: Ottenere tutti gli utenti nell'abbonamento a Microsoft 365 corrente che dispongono di una cassetta postale che non si trova nella città di Bloomington (**Dove {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and $ \_ . City -ne "Bloomington"}**), quindi visualizzare il nome e la città di ognuno.</span><span class="sxs-lookup"><span data-stu-id="3d214-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="3d214-238">Utilizzare caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="3d214-238">Use wildcards</span></span>

<span data-ttu-id="3d214-239">È inoltre possibile utilizzare caratteri jolly nei filtri di PowerShell per trovare una corrispondenza con parte di un nome.</span><span class="sxs-lookup"><span data-stu-id="3d214-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="3d214-240">Si supponga, ad esempio, di cercare un account utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="3d214-241">Tutto quello che puoi ricordare è che il cognome dell'utente era *Anderson* o *forse Henderson* o *Jorgenson.*</span><span class="sxs-lookup"><span data-stu-id="3d214-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="3d214-242">È possibile tenere traccia dell'utente nell'interfaccia di amministrazione di Microsoft 365 usando lo strumento di ricerca ed eseguendo tre diverse ricerche:</span><span class="sxs-lookup"><span data-stu-id="3d214-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="3d214-243">Una per  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="3d214-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="3d214-244">Una per  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="3d214-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="3d214-245">Una per  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="3d214-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="3d214-246">Poiché tutti e tre questi nomi terminano con "son", è possibile indicare a PowerShell di visualizzare tutti gli utenti il cui nome termina con "son".</span><span class="sxs-lookup"><span data-stu-id="3d214-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="3d214-247">Ecco il comando:</span><span class="sxs-lookup"><span data-stu-id="3d214-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="3d214-248">L'interpretazione di questo comando di PowerShell è: Ottenere tutti gli utenti nella sottoscrizione di Microsoft 365 corrente, ma usare un filtro che elenca solo gli utenti il cui cognome termina con "son" (**-Filter '{LastName -like " \* son"}'**).</span><span class="sxs-lookup"><span data-stu-id="3d214-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="3d214-249">\*L'acronimo di qualsiasi set di caratteri, ovvero lettere nel cognome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="3d214-250">PowerShell per Microsoft 365 semplifica la stampa o il salvataggio dei dati</span><span class="sxs-lookup"><span data-stu-id="3d214-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="3d214-251">L'interfaccia di amministrazione di Microsoft 365 consente di visualizzare elenchi di dati.</span><span class="sxs-lookup"><span data-stu-id="3d214-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="3d214-252">Ecco un esempio dell'interfaccia di amministrazione di Skype for Business online che mostra un elenco di utenti abilitati per Skype for Business online:</span><span class="sxs-lookup"><span data-stu-id="3d214-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Esempio di interfaccia di amministrazione di Skype for Business online che mostra un elenco di utenti abilitati a Skype for Business online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="3d214-254">Per salvare le informazioni in un file, è necessario incollarle in un documento o in un foglio di lavoro di Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="3d214-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="3d214-255">In entrambi i casi potrebbe essere necessaria una formattazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="3d214-255">Either case might require additional formatting.</span></span> <span data-ttu-id="3d214-256">Inoltre, l'interfaccia di amministrazione di Microsoft 365 non consente di stampare direttamente l'elenco visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3d214-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="3d214-257">Fortunatamente, è possibile utilizzare PowerShell non solo per visualizzare l'elenco, ma anche per salvarlo in un file facilmente importabile in Excel.</span><span class="sxs-lookup"><span data-stu-id="3d214-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="3d214-258">Ecco un comando di esempio per salvare i dati utente di Skype for Business Online in un file con valori delimitati da virgole (CSV), che può essere facilmente importato come tabella in un foglio di lavoro di Excel:</span><span class="sxs-lookup"><span data-stu-id="3d214-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="3d214-259">Ecco un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="3d214-259">Here's an example of the results:</span></span>
  
![Esempio di tabella importata in un foglio di lavoro di Excel per i dati utente di Skype for Business online salvati in un file con valori delimitati da virgole.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="3d214-261">L'interpretazione di questo comando di PowerShell è: Ottenere tutti gli utenti di Skype for Business online nell'abbonamento a Microsoft 365 corrente (**Get-CsOnlineUser**); ottenere solo il nome utente, l'UPN e il percorso (**Select DisplayName, UserPrincipalName, UsageLocation**); e quindi salvare le informazioni in un file CSV denominato C: \\ Logs \\SfBUsers.csv (**Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation**).</span><span class="sxs-lookup"><span data-stu-id="3d214-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="3d214-262">Puoi anche usare le opzioni per salvare l'elenco come file XML o come pagina HTML.</span><span class="sxs-lookup"><span data-stu-id="3d214-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="3d214-263">Infatti, con altri comandi di PowerShell, è possibile salvarlo direttamente come file di Excel, con qualsiasi formattazione personalizzata desiderata.</span><span class="sxs-lookup"><span data-stu-id="3d214-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="3d214-264">È inoltre possibile inviare l'output di un comando di PowerShell che visualizza un elenco direttamente alla stampante predefinita in Windows.</span><span class="sxs-lookup"><span data-stu-id="3d214-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="3d214-265">Ecco un comando di esempio:</span><span class="sxs-lookup"><span data-stu-id="3d214-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="3d214-266">Di seguito, è riportato l'aspetto del documento stampato:</span><span class="sxs-lookup"><span data-stu-id="3d214-266">Here's what your printed document will look like:</span></span>
  
![Esempio di un documento stampato che rappresenta l'output di un comando di PowerShell inviato direttamente alla stampante predefinita in Windows.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="3d214-268">L'interpretazione di questo comando di PowerShell è: Ottenere tutti gli utenti di Skype for Business online nell'abbonamento a Microsoft 365 corrente; ottenere solo il nome utente, l'UPN e il percorso; e quindi inviare queste informazioni alla stampante predefinita di Windows (**Out-Printer**).</span><span class="sxs-lookup"><span data-stu-id="3d214-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="3d214-269">Il documento stampato ha la stessa formattazione semplice della visualizzazione nella finestra di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d214-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="3d214-270">Per ottenere una copia sul disco rigido, è **sufficiente aggiungere | Out-Printer** fino alla fine del comando.</span><span class="sxs-lookup"><span data-stu-id="3d214-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="3d214-271">PowerShell per Microsoft 365 consente di gestire prodotti server diversi</span><span class="sxs-lookup"><span data-stu-id="3d214-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="3d214-272">I componenti che costituiscono Microsoft 365 sono progettati per funzionare insieme.</span><span class="sxs-lookup"><span data-stu-id="3d214-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="3d214-273">Si supponga, ad esempio, di aggiungere un nuovo utente a Microsoft 365 e di specificare informazioni quali il reparto e il numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="3d214-274">Queste informazioni saranno quindi disponibili se si accede alle informazioni dell'utente in uno dei servizi di Microsoft 365: Skype for Business Online, Exchange o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d214-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="3d214-275">Si tratta di informazioni generali che interessano la famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="3d214-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="3d214-276">Le informazioni specifiche del prodotto, ad esempio le informazioni sulla cassetta postale di Exchange di un utente, in genere non sono disponibili in tutta la famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="3d214-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="3d214-277">Ad esempio, le informazioni sull'abilita o meno della cassetta postale di un utente sono disponibili solo nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3d214-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="3d214-278">Si supponga di voler creare un report che mostra le seguenti informazioni per tutti gli utenti:</span><span class="sxs-lookup"><span data-stu-id="3d214-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="3d214-279">Nome visualizzato dell'utente</span><span class="sxs-lookup"><span data-stu-id="3d214-279">The user's display name</span></span>
    
- <span data-ttu-id="3d214-280">Se l'utente ha una licenza per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d214-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="3d214-281">L'abilitazione della cassetta postale di Exchange dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3d214-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="3d214-282">L'abilitazione per Skype for Business online dell'utente</span><span class="sxs-lookup"><span data-stu-id="3d214-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="3d214-283">Non è possibile produrre facilmente un report di questo tipo nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d214-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3d214-284">Al contrario, è necessario creare un documento separato per archiviare le informazioni, ad esempio un foglio di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="3d214-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="3d214-285">Quindi, ottenere tutti i nomi utente e le informazioni sulla licenza dall'interfaccia di amministrazione di Microsoft 365, ottenere informazioni sulla cassetta postale dall'interfaccia di amministrazione di Exchange, ottenere informazioni su Skype for Business online dall'interfaccia di amministrazione di Skype for Business online e quindi combinare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="3d214-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="3d214-286">L'alternativa consiste nell'usare uno script di PowerShell per compilare il report.</span><span class="sxs-lookup"><span data-stu-id="3d214-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="3d214-287">Lo script di esempio seguente è più complicato rispetto ai comandi visualizzati finora in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3d214-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="3d214-288">Tuttavia, mostra la possibilità di usare PowerShell per creare visualizzazioni delle informazioni difficili da ottenere in altro modo.</span><span class="sxs-lookup"><span data-stu-id="3d214-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="3d214-289">Ecco lo script per compilare e visualizzare l'elenco necessario:</span><span class="sxs-lookup"><span data-stu-id="3d214-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="3d214-290">Ecco un esempio dei risultati:</span><span class="sxs-lookup"><span data-stu-id="3d214-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="3d214-291">L'interpretazione di questo script di PowerShell è:</span><span class="sxs-lookup"><span data-stu-id="3d214-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="3d214-292">Ottenere tutti gli utenti nell'abbonamento a Microsoft 365 corrente e archiviare le informazioni in una variabile denominata *$x* (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="3d214-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="3d214-293">Avviare un ciclo che viene eseguito su tutti gli utenti nella variabile $x (**foreach ($i in $x).**</span><span class="sxs-lookup"><span data-stu-id="3d214-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="3d214-294">Definire una variabile denominata *$y* e archiviare le informazioni sulla cassetta postale dell'utente (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="3d214-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="3d214-295">Aggiungere una nuova proprietà alle informazioni utente denominate *IsMailBoxEnabled.*</span><span class="sxs-lookup"><span data-stu-id="3d214-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="3d214-296">Impostarla sul valore della proprietà IsMailBoxEnabled della cassetta postale dell'utente (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="3d214-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="3d214-297">Definire una variabile denominata *$y* e archiviare le informazioni di Skype for Business online dell'utente (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="3d214-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="3d214-298">Aggiungere una nuova proprietà alle informazioni utente denominate *EnabledForSfB.*</span><span class="sxs-lookup"><span data-stu-id="3d214-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="3d214-299">Impostarla sul valore della proprietà Enabled delle informazioni di Skype for Business online dell'utente (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span><span class="sxs-lookup"><span data-stu-id="3d214-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="3d214-300">Visualizzare l'elenco degli utenti, ma includere solo il nome, se dispongono di una licenza e le due nuove proprietà che indicano se la cassetta postale è abilitata e se sono abilitati per Skype for Business online (**$x | Selezionare DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span><span class="sxs-lookup"><span data-stu-id="3d214-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d214-301">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d214-301">See also</span></span>

[<span data-ttu-id="3d214-302">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d214-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3d214-303">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d214-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3d214-304">Usare Windows PowerShell per creare report in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3d214-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
