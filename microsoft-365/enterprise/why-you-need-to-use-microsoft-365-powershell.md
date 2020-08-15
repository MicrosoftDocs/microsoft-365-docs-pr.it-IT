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
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690974"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="6df42-103">Perché è necessario usare PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df42-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="6df42-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6df42-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6df42-105">Con l'interfaccia di amministrazione di Microsoft 365, è possibile non solo gestire gli account utente e le licenze di Microsoft 365, ma è anche possibile gestire i servizi Microsoft 365 quali Exchange Online, teams e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6df42-105">With the Microsoft 365 admin center, you can not only manage your Microsoft 365 user accounts and licenses, but you can also manage your Microsoft 365 services such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="6df42-106">Tuttavia, è anche possibile gestire questi elementi con i comandi di PowerShell, sfruttando un ambiente di gestione della riga di comando e di scripting per velocità, automazione e funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6df42-106">However, you can also manage these elements with PowerShell commands, taking advantage of a command-line and scripting language environment for speed, automation, and additional capability.</span></span>
  
<span data-ttu-id="6df42-107">In questo articolo verranno illustrati i modi in cui è possibile utilizzare PowerShell per gestire Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="6df42-107">In this article, we'll show you these ways in which you can use PowerShell to manage Microsoft 365:</span></span>
  
- <span data-ttu-id="6df42-108">Rivelare informazioni aggiuntive che non sono visibili con l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df42-108">Reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="6df42-109">Configurare le funzionalità e le impostazioni possibili solo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6df42-109">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="6df42-110">Eseguire operazioni in blocco</span><span class="sxs-lookup"><span data-stu-id="6df42-110">Perform bulk operations</span></span>
    
- <span data-ttu-id="6df42-111">Filtro dei dati</span><span class="sxs-lookup"><span data-stu-id="6df42-111">Filtering data</span></span>
    
- <span data-ttu-id="6df42-112">Stampa o salvataggio dei dati</span><span class="sxs-lookup"><span data-stu-id="6df42-112">Print or save data</span></span>
    
- <span data-ttu-id="6df42-113">Gestire tra i servizi</span><span class="sxs-lookup"><span data-stu-id="6df42-113">Manage across services</span></span>
    
<span data-ttu-id="6df42-114">Prima di iniziare, è necessario comprendere che PowerShell per Microsoft 365 è un insieme di moduli per Windows PowerShell, un ambiente della riga di comando per i servizi e le piattaforme basati su Windows.</span><span class="sxs-lookup"><span data-stu-id="6df42-114">Before you begin, understand that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="6df42-115">Questo ambiente crea una lingua della shell dei comandi che può essere estesa con moduli aggiuntivi e consente di eseguire comandi o script semplici o complessi.</span><span class="sxs-lookup"><span data-stu-id="6df42-115">This environment creates a command shell language that can be extended with additional modules and provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="6df42-116">Ad esempio, dopo aver installato i moduli di PowerShell per Microsoft 365 e aver eseguito la connessione alla sottoscrizione Microsoft 365, è possibile eseguire questo comando per elencare tutte le cassette postali degli utenti per Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="6df42-116">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run this command to list all of the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="6df42-117">La possibilità di ottenere l'elenco delle cassette postali può essere completata facilmente utilizzando l'interfaccia di amministrazione di Microsoft 365, ma il conteggio del numero di elementi in tutti gli elenchi di tutti i siti per tutte le app Web non può essere effettuato facilmente.</span><span class="sxs-lookup"><span data-stu-id="6df42-117">Getting the list of mailboxes can also be easily done using the Microsoft 365 admin center, but counting the number of items in all of the lists for all of the sites for all of your web apps cannot be easily done.</span></span>
  
<span data-ttu-id="6df42-118">Tenere presente che PowerShell per Microsoft 365 è stato creato per aumentare e migliorare la capacità di gestire Microsoft 365, non per sostituire l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6df42-118">Please note that PowerShell for Microsoft 365 is designed to augment and enhance your ability to manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="6df42-119">In qualità di amministratore, è necessario essere almeno a proprio agio nell'utilizzo di PowerShell per Microsoft 365 perché esistono alcune procedure di configurazione che è possibile eseguire solo con i comandi di PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6df42-119">As an administrator, you must become at least comfortable with using PowerShell for Microsoft 365 because there are some configuration procedures that can only be done with PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="6df42-120">In questi casi, verrà richiesto di conoscere le procedure per effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="6df42-120">In these cases, you will be required to understand how to:</span></span>
  
- <span data-ttu-id="6df42-121">Installare i moduli di PowerShell per Microsoft 365 (eseguiti solo una volta per ogni computer di amministratore).</span><span class="sxs-lookup"><span data-stu-id="6df42-121">Install the PowerShell for Microsoft 365 modules (done only once for each administrator computer).</span></span>
    
- <span data-ttu-id="6df42-122">Connettersi alla sottoscrizione Microsoft 365 (operazione eseguita una sola volta per ogni sessione di PowerShell).</span><span class="sxs-lookup"><span data-stu-id="6df42-122">Connect to your Microsoft 365 subscription (done once for each PowerShell session).</span></span>
    
- <span data-ttu-id="6df42-123">Raccogliere le informazioni necessarie per eseguire i comandi di PowerShell necessari per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6df42-123">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="6df42-124">Eseguire correttamente i comandi di PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6df42-124">Run the PowerShell for Microsoft 365 commands successfully.</span></span>
    
<span data-ttu-id="6df42-125">Dopo aver appreso le competenze di base, non è necessario elencare gli utenti delle cassette postali con il comando **Get-Mailbox**, né saper creare un nuovo comando simile a quello precedente per contare tutti gli elementi in tutti gli elenchi di tutti i siti per tutte le app Web.</span><span class="sxs-lookup"><span data-stu-id="6df42-125">After learning these basic skills, you are not required to list your mailbox users with **Get-Mailbox** command, nor are you required to understand how to create a new command like the previous one to count all the items in all the lists for all of the sites for all of your web apps.</span></span> <span data-ttu-id="6df42-126">Microsoft e la community di amministratori possono aiutarti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6df42-126">Microsoft and the community of administrators can help you with that as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="6df42-127">PowerShell per Microsoft 365 è in grado di rivelare informazioni aggiuntive che non sono visibili con l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df42-127">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="6df42-128">L'interfaccia di amministrazione di Microsoft 365 Visualizza molte informazioni utili, ma ciò non significa che Visualizza tutte le informazioni possibili che Microsoft 365 archivia su utenti, licenze, cassette postali e siti.</span><span class="sxs-lookup"><span data-stu-id="6df42-128">The Microsoft 365 admin center displays a lot of useful information, but that doesn't mean that it displays all the possible information that Microsoft 365 stores on users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="6df42-129">Di seguito è riportato un esempio per **gli utenti e i gruppi** nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="6df42-129">Here is an example for **users and groups** in the Microsoft 365 admin center:</span></span>
  
![Esempio di visualizzazione di utenti e gruppi nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="6df42-131">Per diversi scopi, verranno visualizzate le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="6df42-131">For many purposes, this displays the information you need to know.</span></span> <span data-ttu-id="6df42-132">Tuttavia, in alcuni casi sono necessarie informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6df42-132">However, there are times when you need more.</span></span> <span data-ttu-id="6df42-133">Ad esempio, le licenze Microsoft 365 (e le funzionalità di Microsoft 365 disponibili per un utente) dipendono in parte dalla posizione geografica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6df42-133">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depend in part on that user's geographic location.</span></span> <span data-ttu-id="6df42-134">I criteri e le funzionalità che è possibile estendere a un utente che vive negli Stati Uniti potrebbero non essere gli stessi per un utente che risiede in India o Belgio.</span><span class="sxs-lookup"><span data-stu-id="6df42-134">The policies and features you can extend to a user who lives in the United States might not be the same as the policies and features you can extend to a user who lives in India or in Belgium.</span></span> <span data-ttu-id="6df42-135">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per determinare la posizione geografica di un utente con questa procedura:</span><span class="sxs-lookup"><span data-stu-id="6df42-135">You can use the Microsoft 365 admin center to determine a user's geographic location with these steps:</span></span>
  
1. <span data-ttu-id="6df42-136">Fare doppio clic sul **Nome visualizzato** dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6df42-136">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="6df42-137">Nelle proprietà del riquadro di visualizzazione dell'utente, fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6df42-137">In the user properties display pane, click **details**.</span></span>
    
3. <span data-ttu-id="6df42-138">Nella visualizzazione dettagli, fare clic su **ulteriori dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6df42-138">In the details display, click **additional details**.</span></span>
    
4. <span data-ttu-id="6df42-139">Scorrere verso il basso fino a quando non viene visualizzata l'intestazione **Paese o regione**:</span><span class="sxs-lookup"><span data-stu-id="6df42-139">Scroll down until you see the heading **Country or region**:</span></span>
    
     ![Esempio di informazioni sull'area geografica per un utente nell'interfaccia di amministrazione di Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="6df42-141">Prendere nota del nome visualizzato e della posizione dell'utente su un pezzo di carta o copiarlo e incollarlo nel Blocco note.</span><span class="sxs-lookup"><span data-stu-id="6df42-141">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span> 
    
<span data-ttu-id="6df42-142">È necessario ripetere questa procedura per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="6df42-142">You must repeat this procedure for each user.</span></span> <span data-ttu-id="6df42-143">Per molti utenti, potrebbe trattarsi di un'attività noiosa.</span><span class="sxs-lookup"><span data-stu-id="6df42-143">For many users, this can be a tedious task.</span></span> <span data-ttu-id="6df42-144">Con PowerShell per Microsoft 365, è possibile visualizzare queste informazioni per tutti gli utenti con il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="6df42-144">With PowerShell for Microsoft 365, you can display this information for all of your users with the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="6df42-145">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="6df42-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="6df42-146">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df42-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="6df42-147">Ecco un esempio di visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="6df42-147">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="6df42-148">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente ( **Get-AzureADUser** ), ma visualizzare solo il nome e la posizione di ogni utente ( **Select DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-148">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription ( **Get-AzureADUser** ), but only display the name and location for each user ( **Select DisplayName, UsageLocation** ).</span></span>
  
<span data-ttu-id="6df42-149">Poiché PowerShell per Microsoft 365 supporta una lingua di shell dei comandi, è possibile modificare ulteriormente le informazioni ottenute dal comando **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="6df42-149">Because PowerShell for Microsoft 365 supports a command shell language, you can further manipulate the information obtained from the **Get-AzureADUser** command.</span></span> <span data-ttu-id="6df42-150">Ad esempio, se si desidera ordinare gli utenti in base alla propria posizione, raggruppare tutti gli utenti brasiliani insieme, tutti gli utenti degli Stati Uniti e così via. Di seguito è riportato il comando:</span><span class="sxs-lookup"><span data-stu-id="6df42-150">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, etc. Here is the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="6df42-151">Ecco un esempio di visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="6df42-151">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="6df42-152">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente, ma visualizzare solo il nome e la posizione di ogni utente e ordinarli in primo luogo in base alla posizione e quindi ai rispettivi nomi ( **Sort UsageLocation, DisplayName** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location, and then their names ( **Sort UsageLocation, DisplayName** ).</span></span>
  
<span data-ttu-id="6df42-p110">È inoltre possibile utilizzare altre opzioni di filtro. Ad esempio, se si desidera visualizzare tali informazioni sugli utenti residenti in Brasile, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="6df42-p110">You can also employ additional filtering. For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="6df42-155">Ecco un esempio di visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="6df42-155">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  <span data-ttu-id="6df42-156">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente la cui posizione è il Brasile ( **dove {$ \_ . UsageLocation-EQ "BR"}** ), quindi visualizzare il nome e la posizione di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="6df42-156">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription whose location is Brazil ( **Where {$\_.UsageLocation -eq "BR"}** ), then display the name and location for each user.</span></span>
  
 <span data-ttu-id="6df42-157">**Nota rapida riguardo i domini più grandi**</span><span class="sxs-lookup"><span data-stu-id="6df42-157">**A Quick Note Regarding Larger Domains**</span></span>
  
<span data-ttu-id="6df42-158">Se si dispone di un dominio di grandi dimensioni, con decine di migliaia di utenti, alcuni degli esempi mostrati in questo articolo potrebbero causare una "limitazione".</span><span class="sxs-lookup"><span data-stu-id="6df42-158">If you have a very large domain with tens of thousands of users, trying some of the examples we show in this article could lead to "throttling."</span></span> <span data-ttu-id="6df42-159">Ciò significa che, in base a dati come la potenza di elaborazione e lunghezza di banda disponibile, si sta cercando di effettuare troppe operazioni contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6df42-159">That means that, based on things like computing power and available network bandwidth, you're trying to do a little too much at one time.</span></span> <span data-ttu-id="6df42-160">Per questo motivo, le organizzazioni di grandi dimensioni potrebbero voler dividere alcuni di questi comandi PowerShell per Microsoft 365 in due comandi.</span><span class="sxs-lookup"><span data-stu-id="6df42-160">Because of that, larger organizations might want to split some of these PowerShell for Microsoft 365 commands into two commands.</span></span> <span data-ttu-id="6df42-161">Ad esempio, questo comando restituisce tutti gli account utente e mostra il nome e la posizione di ciascun utente:</span><span class="sxs-lookup"><span data-stu-id="6df42-161">For example, this one command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="6df42-p112">Questa operazione funziona perfettamente per i domini più piccoli. Nelle organizzazioni di grandi dimensioni, tuttavia, potrebbe essere necessario dividerlo in due comandi: un comando per archiviare le informazioni sugli account utente in una variabile, l'altro per visualizzare le informazioni necessarie. Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="6df42-p112">That works great for smaller domains. In a large organization, however, you might need to split that into two commands: one command to store the user account information in a variable and another command to display the needed information. Here is an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="6df42-165">L'interpretazione di questo set di comandi di PowerShell è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6df42-165">The interpretation of this set of PowerShell commands is:</span></span>
- <span data-ttu-id="6df42-166">Ottenere tutti gli utenti nella sottoscrizione Microsoft 365 corrente e archiviare le informazioni in una variabile denominata $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-166">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="6df42-167">Visualizzare il contenuto della variabile $x, ma includere solo il nome e la posizione di ciascun utente ( **$x | Select DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-167">Display the contents of the variable $x, but only include the name and location for each user ( **$x | Select DisplayName, UsageLocation** ).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="6df42-168">Microsoft 365 dispone di funzionalità che è possibile configurare solo con PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df42-168">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="6df42-169">L'interfaccia di amministrazione di Microsoft 365 ha lo scopo di consentire l'accesso alle attività amministrative più comuni o significative che si applicano alla maggior parte delle persone.</span><span class="sxs-lookup"><span data-stu-id="6df42-169">The Microsoft 365 admin center is intended to provide access to the most common or meaningful administrative tasks that apply to most people.</span></span> <span data-ttu-id="6df42-170">In altre parole, l'interfaccia di amministrazione di Microsoft 365 è stata progettata in modo che l'amministratore comune potesse utilizzare lo strumento per eseguire le attività di gestione più comuni.</span><span class="sxs-lookup"><span data-stu-id="6df42-170">In other words, the Microsoft 365 admin center was designed so that the typical administrator could use the tool to carry out the most common management tasks.</span></span> <span data-ttu-id="6df42-171">In base a questa definizione, significa che sono presenti alcune attività che non possono essere completate tramite l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6df42-171">By this definition, that means that there are some tasks that can't be completed by using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="6df42-172">Ad esempio, l'interfaccia di amministrazione di Skype for Business online offre alcune opzioni per la creazione di convocazioni di riunioni personalizzate:</span><span class="sxs-lookup"><span data-stu-id="6df42-172">For example, the Skype for Business Online Admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Esempio di visualizzazione di inviti personalizzati a riunioni nell’interfaccia di amministrazione di Skype for Business online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="6df42-p114">Con queste impostazioni, è possibile aggiungere un tocco di personalizzazione e professionalità alle convocazioni di riunioni. Tuttavia, esistono più impostazioni di configurazione di una riunione rispetto alla semplice creazione di convocazioni personalizzate. Ad esempio, per impostazione predefinita le riunioni consentono:</span><span class="sxs-lookup"><span data-stu-id="6df42-p114">With these settings, you can add a touch of personalization and professionalism to meeting invitations. However, there's more to meeting configuration settings than simply creating custom meeting invitations. For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="6df42-177">A utenti anonimi di ottenere l'ingresso automatico a ogni riunione.</span><span class="sxs-lookup"><span data-stu-id="6df42-177">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="6df42-178">Ai partecipanti di registrare una riunione.</span><span class="sxs-lookup"><span data-stu-id="6df42-178">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="6df42-179">A tutti gli utenti dell'organizzazione di essere designati come relatori quando partecipano a riunione.</span><span class="sxs-lookup"><span data-stu-id="6df42-179">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="6df42-180">Queste impostazioni non sono disponibili dall'interfaccia di amministrazione di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="6df42-180">These settings are not available from the Skype for Business Online Admin center.</span></span> <span data-ttu-id="6df42-181">Tuttavia, è possibile controllarli da PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6df42-181">However, you can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="6df42-182">Ecco un comando che consente di disabilitare queste tre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="6df42-182">Here is a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="6df42-183">Questo comando richiede l'installazione del [modulo di PowerShell per Skype for Business Online ](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="6df42-183">This command requires that you install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="6df42-184">L'interpretazione di questo comando PowerShell è la seguente: per le impostazioni per le nuove riunioni di Skype for business online ( **Set-CsMeetingConfiguration** ), disabilitare l'accesso degli utenti anonimi alle riunioni (- **AdmitAnonymousUsersByDefault $false** ), disabilitare la possibilità per i partecipanti di registrare le riunioni ( **-AllowConferenceRecording $false** ) e non designare tutti gli utenti dell'organizzazione come relatori ( **-DesignateAsPresenter "None"** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-184">The interpretation of this PowerShell command is: For the settings for new Skype for Business Online meetings ( **Set-CsMeetingConfiguration** ), disable allowing anonymous users to gain automatic entrance to meetings ( **-AdmitAnonymousUsersByDefault $False** ), disable the ability for attendees to record meetings ( **-AllowConferenceRecording $False** ), and do not designate all users from your organization as presenters ( **-DesignateAsPresenter "None"** ).</span></span>
  
<span data-ttu-id="6df42-185">Se si cambia idea e si desidera ripristinare le impostazioni predefinite (tutte abilitate), sarà sufficiente eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="6df42-185">If you change your mind and want to restore these default settings (all of them enabled), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="6df42-186">Questo è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="6df42-186">This is just one example.</span></span> <span data-ttu-id="6df42-187">Ve ne sono altri, ed è il motivo per cui, in quanto amministratore, è necessario avere dimestichezza con i comandi di PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6df42-187">There are others, which is why you, as an administrator, need to be comfortable with running PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a><span data-ttu-id="6df42-188">PowerShell per Microsoft 365 è molto utile per eseguire operazioni in blocco</span><span class="sxs-lookup"><span data-stu-id="6df42-188">PowerShell for Microsoft 365 is great at carrying out bulk operations</span></span>

<span data-ttu-id="6df42-189">Storicamente, le interfacce visive come l'interfaccia di amministrazione di Microsoft 365 sono più importanti quando si ha un'unica operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="6df42-189">Historically, visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to perform.</span></span> <span data-ttu-id="6df42-190">Ad esempio, se è necessario disabilitare un account utente, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per individuare e cancellare rapidamente una casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="6df42-190">For example, if you need to disable one user account, you can use the Microsoft 365 admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="6df42-191">Questo può essere più semplice rispetto all'esecuzione di un'operazione analoga in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df42-191">This can be simpler than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="6df42-192">Tuttavia, se è necessario modificare molte cose o alcuni elementi selezionati all'interno di un insieme di grandi dimensioni, è possibile che l'interfaccia di amministrazione di Microsoft 365 non sia il miglior utilizzo del proprio tempo.</span><span class="sxs-lookup"><span data-stu-id="6df42-192">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best use of your time.</span></span> <span data-ttu-id="6df42-193">Ad esempio, se è stato necessario cambiare il prefisso su migliaia di numeri di telefono o se è necessario rimuovere un utente specifico, Ken remario, da tutti i siti di SharePoint Online, come è possibile eseguire tale operazione nell'interfaccia di amministrazione di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="6df42-193">For example, if you had to change the prefix on thousands of phone numbers or you needed to remove a specific user, Ken Myer, from all of your SharePoint Online sites, how would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="6df42-194">Per quanto riguarda l'ultimo esempio, sono presenti diverse centinaia di siti di SharePoint Online e non si sa nemmeno di quali di questi siti è membro Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="6df42-194">For the latter example, you have several hundred SharePoint Online sites and you don't know even know which ones of which Ken Meyer is a member.</span></span> <span data-ttu-id="6df42-195">Questo significa che sarà necessario iniziare dall'interfaccia di amministrazione di Microsoft 365 e quindi eseguire questa procedura per ogni sito:</span><span class="sxs-lookup"><span data-stu-id="6df42-195">That means you'll have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="6df42-196">Fare clic sull' **URL** del sito.</span><span class="sxs-lookup"><span data-stu-id="6df42-196">Click the **URL** of the site.</span></span>
    
2. <span data-ttu-id="6df42-197">Nella casella **proprietà della raccolta del sito**, fare clic sul link **Indirizzo sito Web** per aprire il sito.</span><span class="sxs-lookup"><span data-stu-id="6df42-197">In the **site collection properties** box, click the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="6df42-198">Nel sito, fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="6df42-198">On the site, click **Share**.</span></span>
    
4. <span data-ttu-id="6df42-199">Nella finestra di dialogo **Condividi** fare clic sul link che mostra tutti gli utenti che dispongono delle autorizzazioni per il sito:</span><span class="sxs-lookup"><span data-stu-id="6df42-199">In the **Share** dialog box click the link that shows you all the users who have permissions to the site:</span></span>
    
     ![Esempio di visualizzazione di membri del sito SharePoint Online nell'interfaccia di amministrazione di SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="6df42-201">Nella finestra di dialogo **Condiviso con** fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="6df42-201">In the **Shared With** dialog box, click **Advanced**.</span></span>
    
6. <span data-ttu-id="6df42-202">Scorrere l'elenco degli utenti, trovare e selezionare Ken Myer (presumendo che disponga delle autorizzazioni per il sito), quindi fare clic su **Rimuovi autorizzazioni utente**.</span><span class="sxs-lookup"><span data-stu-id="6df42-202">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then click **Remove User Permissions**.</span></span>
    
<span data-ttu-id="6df42-203">La procedura può richiedere molto tempo per diverse centinaia di siti.</span><span class="sxs-lookup"><span data-stu-id="6df42-203">This can take a long time for several hundred sites.</span></span>
  
<span data-ttu-id="6df42-204">L'alternativa consiste nell'usare PowerShell per Microsoft 365 e il seguente comando per rimuovere Ken remario da tutti i siti:</span><span class="sxs-lookup"><span data-stu-id="6df42-204">The alternative is to use PowerShell for Microsoft 365 and the following command to remove Ken Myer from all of your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="6df42-205">Questo comando richiede l'installazione del [modulo di PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="6df42-205">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="6df42-206">L'interpretazione di questo comando di PowerShell è: recuperare tutti i siti di SharePoint nella sottoscrizione Microsoft 365 corrente ( **Get-SPOSite** ) e per ogni sito, rimuovere Ken Meyer dall'elenco degli utenti che possono accedervi ( **foreach {Remove-consorter-site $ \_ . URL-LoginName "kenmyer@litwareinc.com"}** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-206">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription ( **Get-SPOSite** ) and for each site, remove Ken Meyer from the list of users who can access it ( **ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer@litwareinc.com"}** ).</span></span>
  
<span data-ttu-id="6df42-207">Poiché si dice a Microsoft 365 di rimuovere Ken Meyer da ogni sito, compresi quelli in cui non ha accesso, la visualizzazione di questo comando mostrerà gli errori per i siti in cui attualmente non ha accesso.</span><span class="sxs-lookup"><span data-stu-id="6df42-207">Because we are telling Microsoft 365 to remove Ken Meyer from every site, including those in which he does not have access, the display of this command will show errors for those sites in which he does not currently have access.</span></span> <span data-ttu-id="6df42-208">È possibile utilizzare una condizione aggiuntiva su questo comando, per rimuovere Ken Meyer solo dai siti in cui compare nell'elenco degli accessi, ma gli errori elencati non danneggiano i siti.</span><span class="sxs-lookup"><span data-stu-id="6df42-208">We can use an additional condition on this command to remove Key Meyer only from the sites that have him in their login list, but the listed errors cause no harm to the sites themselves.</span></span> <span data-ttu-id="6df42-209">Questo comando potrebbe richiedere alcuni minuti per l'esecuzione in centinaia di siti anziché ore di utilizzo dell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6df42-209">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="6df42-p121">Ecco un altro esempio di operazione di massa. Utilizzare questo comando per aggiungere Bonnie Kearney, un nuovo amministratore di SharePoint, a tutti i siti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="6df42-p121">Here is another bulk operation example. Use this command to add Bonnie Kearney, a new SharePoint administrator, to all of the sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  <span data-ttu-id="6df42-212">L'interpretazione di questo comando di PowerShell è: recuperare tutti i siti di SharePoint nella sottoscrizione corrente di Microsoft 365 e per ogni sito, consentire a Bonnie Kearney di accedere aggiungendo il nome di accesso al gruppo membri del sito ( **foreach {Add-Consorter-site $ \_ . URL-LoginName "bkearney@litwareinc.com"-gruppo "membri"}** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-212">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription and for each site, allow Bonnie Kearney access by adding her login name to the Members group of the site ( **ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}** ).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="6df42-213">PowerShell per Microsoft 365 è ottimo per filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="6df42-213">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="6df42-214">L'interfaccia di amministrazione di Microsoft 365 offre diversi modi per filtrare i dati in modo da individuare rapidamente e facilmente un sottoinsieme di informazioni mirato.</span><span class="sxs-lookup"><span data-stu-id="6df42-214">The Microsoft 365 admin center provides several different ways to filter your data to quickly and easily locate a targeted subset of information.</span></span> <span data-ttu-id="6df42-215">Ad esempio, Exchange facilita il filtro di qualsiasi proprietà relativa alla cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="6df42-215">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="6df42-216">Ad esempio, questo è un elenco delle cassette postali degli utenti che vivono nella città di Bloomington:</span><span class="sxs-lookup"><span data-stu-id="6df42-216">For example, here is the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Esempio di ricerca avanzata nell'interfaccia di amministrazione di Microsoft 365 per l'elenco delle cassette postali per tutti gli utenti che vivono nella città di Bloomington.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="6df42-p123">L'interfaccia di amministrazione di Exchange consente di combinare i criteri di filtro. Ad esempio, è possibile trovare le cassette postali di tutti i residenti di Bloomington e di coloro che lavorano nel reparto finanziario.</span><span class="sxs-lookup"><span data-stu-id="6df42-p123">The Exchange Admin center also lets you combine filter criteria. For example, you can find the mailboxes for all the people who live in Bloomington and who work in the Finance department.</span></span> 
  
<span data-ttu-id="6df42-p124">Tuttavia, esistono limitazioni per le operazioni che è possibile eseguire nell'interfaccia di amministrazione di Exchange. Ad esempio, si potrebbe desiderare di individuare le cassette postali di persone che vivono a Bloomington o San Diego oppure le cassette postali di tutte le persone non residenti a Bloomington.</span><span class="sxs-lookup"><span data-stu-id="6df42-p124">However, there are limitations to what you can do in the Exchange Admin center. For example, maybe you'd like to find the mailboxes of people who live in Bloomington or San Diego, or the mailboxes for all the people who don't live in Bloomington.</span></span> 
  
<span data-ttu-id="6df42-222">Con PowerShell per Microsoft 365, è possibile ottenere un elenco delle cassette postali per tutte le persone che vivono nelle città di Bloomington o San Diego con questo comando:</span><span class="sxs-lookup"><span data-stu-id="6df42-222">With PowerShell for Microsoft 365, you can get a list of mailboxes for all the people who live in the cities of Bloomington or San Diego with this command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="6df42-223">Ecco un esempio di visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="6df42-223">Here is an example of the display:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  <span data-ttu-id="6df42-224">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nell'attuale sottoscrizione di Microsoft 365 che dispongono di una cassetta postale nelle città di San Diego o Bloomington ( **dove {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-and ($ \_ . City-EQ "San Diego"-oppure $ \_ . City-EQ "Bloomington")}** ), quindi visualizzare il nome e la città per ognuno ( **selezionare DisplayName, City** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-224">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox in the cities of either San Diego or Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}** ), then display the name and city for each ( **Select DisplayName, City** ).</span></span>
  
<span data-ttu-id="6df42-225">Il comando di seguito consente di elencare tutte le cassette postali delle persone che vivono in qualsiasi altro posto a eccezione di Bloomington:</span><span class="sxs-lookup"><span data-stu-id="6df42-225">To list all the mailboxes for people who live anywhere except Bloomington, here is the command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="6df42-226">Ecco un esempio di visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="6df42-226">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="6df42-227">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nell'attuale sottoscrizione di Microsoft 365 che dispongono di una cassetta postale che non si trova nella città di Bloomington ( **dove {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-e $ \_ . City-ne "Bloomington"}** ), quindi visualizzare il nome e la città per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="6df42-227">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}** ), then display the name and city for each.</span></span>
  
<span data-ttu-id="6df42-228">È inoltre possibile utilizzare i caratteri jolly nei filtri di PowerShell per far corrispondere parte di un nome.</span><span class="sxs-lookup"><span data-stu-id="6df42-228">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="6df42-229">Ad esempio, si supponga di effettuare la ricerca di un account utente e di ricordare solo che il cognome potrebbe corrispondere ad Anderson o forse a Henderson oppure Jorgenson.</span><span class="sxs-lookup"><span data-stu-id="6df42-229">For example, suppose you're looking for a user account, and all you can remember is that their last name was Anderson, or maybe Henderson, or maybe it was Jorgenson.</span></span>
  
<span data-ttu-id="6df42-230">È possibile rintracciare l'utente nell'interfaccia di amministrazione di Microsoft 365 utilizzando lo strumento di ricerca ed effettuando tre ricerche diverse:</span><span class="sxs-lookup"><span data-stu-id="6df42-230">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="6df42-231">Una per  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="6df42-231">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="6df42-232">Una per  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="6df42-232">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="6df42-233">Una per  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="6df42-233">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="6df42-234">Poiché tutti e tre questi nomi terminano con "son", è possibile indicare a PowerShell di visualizzare tutti gli utenti il cui nome termina con "son".</span><span class="sxs-lookup"><span data-stu-id="6df42-234">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="6df42-235">Ecco il comando:</span><span class="sxs-lookup"><span data-stu-id="6df42-235">Here is the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  <span data-ttu-id="6df42-236">L'interpretazione di questo comando di PowerShell è: recuperare tutti gli utenti nella sottoscrizione Microsoft 365 corrente, ma utilizzare un filtro che elenca solo gli utenti i cui cognomi terminano con "son" ( **-Filter ' {LastName-like " \* son"}'** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-236">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" ( **-Filter '{LastName -like "\*son"}'** ).</span></span> <span data-ttu-id="6df42-237">Gli \* stand per qualsiasi set di caratteri, ovvero lettere nel caso del cognome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6df42-237">The \* stands for any set of characters, which are letters in the case of the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="6df42-238">PowerShell per Microsoft 365 rende più semplice la stampa o il salvataggio dei dati</span><span class="sxs-lookup"><span data-stu-id="6df42-238">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="6df42-239">L'interfaccia di amministrazione di Microsoft 365 consente di visualizzare gli elenchi di dati.</span><span class="sxs-lookup"><span data-stu-id="6df42-239">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="6df42-240">Ecco un esempio dell'interfaccia di amministrazione di Skype for Business online che mostra un elenco di utenti che sono stati abilitati per Skype for Business online:</span><span class="sxs-lookup"><span data-stu-id="6df42-240">Here is an example of the Skype for Business Online Admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Esempio di interfaccia di amministrazione di Skype for Business online che mostra un elenco di utenti abilitati a Skype for Business online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="6df42-242">Per salvare queste informazioni in un file, è necessario copiarle e incollarle in un documento o in Excel.</span><span class="sxs-lookup"><span data-stu-id="6df42-242">To save that information to a file, you must copy and paste it into a document or Excel.</span></span> <span data-ttu-id="6df42-243">In entrambi i casi, la copia potrebbe richiedere ulteriore formattazione.</span><span class="sxs-lookup"><span data-stu-id="6df42-243">In either case, the copy might require additional formatting.</span></span> <span data-ttu-id="6df42-244">Inoltre, l'interfaccia di amministrazione di Microsoft 365 non consente di stampare direttamente l'elenco visualizzato.</span><span class="sxs-lookup"><span data-stu-id="6df42-244">Additionally, the Microsoft 365 admin center does not provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="6df42-245">Fortunatamente, è possibile utilizzare PowerShell per non solo visualizzare l'elenco, ma salvarlo in un file che può essere importato facilmente in Excel.</span><span class="sxs-lookup"><span data-stu-id="6df42-245">Fortunately, you can use PowerShell to not only display the list, but save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="6df42-246">Ecco un comando di esempio per salvare i dati utente di Skype for Business online in un file con valori delimitati da virgole (CSV), che può essere facilmente importato come tabella in un foglio di lavoro di Excel:</span><span class="sxs-lookup"><span data-stu-id="6df42-246">Here is an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, a file that can be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="6df42-247">Ecco un esempio di visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="6df42-247">Here is an example of the display:</span></span>
  
![Esempio di tabella importata in un foglio Excel di dati di utenti di Skype for Business online, salvati in un file con valori delimitati da virgole (CSV).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  <span data-ttu-id="6df42-249">L'interpretazione di questo comando di PowerShell è: ottenere tutti gli utenti di Skype for business online nella sottoscrizione Microsoft 365 corrente ( **Get-CsOnlineUser** ), ottenere solo il nome utente, l'UPN e la posizione ( **selezionare DisplayName, userPrincipalName, UsageLocation** ) e quindi salvare tali informazioni nel file CSV denominato c: \\ logs \\SfBUsers.csv ( **Export-CSV-path "c: \\ logs \\SfBUsers.csv"-NoTypeInformation** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-249">The interpretation of this PowerShell command is: Get all of the Skype for Business Online users in the current Microsoft 365 subscription ( **Get-CsOnlineUser** ), obtain only the user name, UPN, and location ( **Select DisplayName, UserPrincipalName, UsageLocation** ), and then save that information in CSV file named C:\\Logs\\SfBUsers.csv ( **Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation** ).</span></span>
  
<span data-ttu-id="6df42-p131">È anche possibile utilizzare le opzioni per salvare questo elenco come file XML o pagina HTML. Infatti, con altri comandi di PowerShell, è possibile salvarlo direttamente come file di Excel, con qualsiasi formattazione personalizzata che si desidera.</span><span class="sxs-lookup"><span data-stu-id="6df42-p131">You can also use options to save this list as an XML file or as an HTML page. In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you desire.</span></span> 
  
<span data-ttu-id="6df42-252">È anche possibile inviare l'output di un comando di PowerShell che consente di visualizzare un elenco direttamente alla stampante predefinita in Windows.</span><span class="sxs-lookup"><span data-stu-id="6df42-252">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="6df42-253">Ecco un esempio di comando:</span><span class="sxs-lookup"><span data-stu-id="6df42-253">Here is an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="6df42-254">Di seguito, è riportato l'aspetto del documento stampato:</span><span class="sxs-lookup"><span data-stu-id="6df42-254">Here's what your printed document will look like:</span></span>
  
![Esempio di un documento stampato che è stato l'output di un comando di PowerShell elencato direttamente alla stampante predefinita in Windows.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  <span data-ttu-id="6df42-256">L'interpretazione di questo comando di PowerShell è: ottenere tutti gli utenti di Skype for business online nella sottoscrizione Microsoft 365 corrente, ottenere solo il nome utente, l'UPN e la posizione, quindi inviare tali informazioni alla stampante predefinita di Windows ( **fuori stampante** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-256">The interpretation of this PowerShell command is:  Get all of the Skype for Business Online users in the current Microsoft 365 subscription, obtain only the user name, UPN, and location, and then send that information to the default Windows printer ( **Out-Printer** ).</span></span>
  
<span data-ttu-id="6df42-257">Il documento stampato ha la stessa formattazione semplice della visualizzazione all'interno della finestra di comando di PowerShell, ma dopo aver creato un comando di PowerShell per elencare gli elementi necessari, è sufficiente aggiungere **| Out-Printer** alla fine del comando per ottenere una copia cartacea da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="6df42-257">The printed document has the same simple formatting as the display within the PowerShell command window, but once you have created a PowerShell command to list what you need, you just add **| Out-Printer** to the end of the command to get a hard copy to work from.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="6df42-258">PowerShell per Microsoft 365 consente di gestire diversi prodotti server</span><span class="sxs-lookup"><span data-stu-id="6df42-258">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="6df42-259">I diversi componenti che compongono Microsoft 365 sono stati concepiti per funzionare insieme.</span><span class="sxs-lookup"><span data-stu-id="6df42-259">The different components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="6df42-260">Si supponga, ad esempio, di aggiungere un nuovo utente a Microsoft 365 e, in tal caso, di specificare tali informazioni come reparto e numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6df42-260">For example, suppose you add a new user to Microsoft 365 and, when you do, you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="6df42-261">Tali informazioni saranno quindi disponibili se si accede alle informazioni dell'utente utilizzando uno qualsiasi dei servizi Microsoft 365: Skype for business online, Exchange o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6df42-261">That information will then be available if you access the user's information using any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint Online.</span></span>
  
<span data-ttu-id="6df42-p134">Si tratta di informazioni generali che interessano la famiglia di prodotti. Le informazioni specifiche di un prodotto, ad esempio quelle relative alla cassetta postale di Exchange di un utente, non sono generalmente disponibili tra le famiglie di prodotti. Ad esempio, se si desidera sapere se la cassetta postale di un utente è abilitata o meno, tale informazione è disponibile solo nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="6df42-p134">But that's for common information that spans the suite of products. Product-specific information-for example, information about a user's Exchange mailbox-is typically not available across the suite. For example, if you want to know if a user's mailbox is enabled or not, that information is available only in the Exchange Admin center.</span></span> 
  
<span data-ttu-id="6df42-265">Si supponga di voler creare un report che mostra le seguenti informazioni per tutti gli utenti:</span><span class="sxs-lookup"><span data-stu-id="6df42-265">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="6df42-266">Nome visualizzato dell'utente</span><span class="sxs-lookup"><span data-stu-id="6df42-266">The user's display name</span></span>
    
- <span data-ttu-id="6df42-267">Se l'utente ha una licenza per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df42-267">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="6df42-268">L'abilitazione della cassetta postale di Exchange dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6df42-268">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="6df42-269">L'abilitazione per Skype for Business online dell'utente</span><span class="sxs-lookup"><span data-stu-id="6df42-269">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="6df42-270">Al momento non è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per produrre facilmente un rapporto di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="6df42-270">You currently cannot use the Microsoft 365 admin center to easily produce such a report.</span></span> <span data-ttu-id="6df42-271">Al contrario, è necessario creare un documento separato per archiviare le informazioni, ad esempio un foglio di lavoro di Excel, e ottenere tutti i nomi utente e le informazioni di licenza dall'interfaccia di amministrazione di Microsoft 365, ottenere le informazioni della cassetta postale dall'interfaccia di amministrazione di Exchange, ottenere informazioni su Skype for business online dal centro di amministrazione di Skype for business online, quindi raccogliere e combinare tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="6df42-271">Instead, you'll have to create a separate document to store the information, like an Excel worksheet, and get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then collate and combine that information.</span></span>
  
<span data-ttu-id="6df42-272">L'alternativa consiste nell'usare uno script di PowerShell per compilare il report.</span><span class="sxs-lookup"><span data-stu-id="6df42-272">The alternative is to use a PowerShell script to compile that report for you.</span></span>
  
<span data-ttu-id="6df42-273">Il seguente script di esempio è più complesso dei comandi che finora sono stati illustrati in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="6df42-273">The following example script is more complicated than the commands you have seen so far in this article.</span></span> <span data-ttu-id="6df42-274">Tuttavia, dimostra la potenzialità dell'utilizzo di PowerShell per creare visualizzazioni di informazioni che sono molto difficili da fare altrimenti.</span><span class="sxs-lookup"><span data-stu-id="6df42-274">But, it shows the potential of using PowerShell to create views of information that are very difficult to do otherwise.</span></span> <span data-ttu-id="6df42-275">Ecco lo script in grado di compilare e visualizzare l'elenco necessario:</span><span class="sxs-lookup"><span data-stu-id="6df42-275">Here is the script that can compile and display the needed list:</span></span>
  
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

<span data-ttu-id="6df42-276">Ecco un esempio di visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="6df42-276">Here is an example of the display:</span></span>
  
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

<span data-ttu-id="6df42-277">L'interpretazione di questo script di PowerShell è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6df42-277">The interpretation of this PowerShell script is:</span></span>  

- <span data-ttu-id="6df42-278">Ottenere tutti gli utenti nella sottoscrizione Microsoft 365 corrente e archiviare le informazioni in una variabile denominata $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-278">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="6df42-279">Avviare un ciclo che viene eseguito su tutti gli utenti nella variabile denominata $x ( **foreach ($i in $x)** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-279">Start a loop that runs over all the users in the variable named $x ( **foreach ($i in $x)** ).</span></span>  
- <span data-ttu-id="6df42-280">Definire una variabile denominata $y e archiviarvi all'interno le informazioni sulla cassetta postale dell'utente ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-280">Define a variable named $y and store the user's mailbox information in it ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="6df42-281">Aggiungere una nuova proprietà alle informazioni sull'utente denominata IsMailBoxEnabled e impostarla sul valore della proprietà IsMailBoxEnabled della cassetta postale dell'utente ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-281">Add a new property to the user information named IsMailBoxEnabled and set it to the value of the IsMailBoxEnabled property of the user's mailbox ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).</span></span>
- <span data-ttu-id="6df42-282">Definire una variabile denominata $y e archiviarvi all'interno le informazioni su Skype for Business Online relative all'utente ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-282">Define a variable named $y and store the user's Skype for Business Online information in it ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="6df42-283">Aggiungere una nuova proprietà alle informazioni sull'utente denominata EnabledForSfB e impostarla sul valore della proprietà EnabledForSfB della cassetta postale dell'utente di Skype for Business Online ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-283">Add a new property to the user information named EnabledForSfB and set it to the value of the Enabled property of the user's Skype for Business Online information ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).</span></span>
- <span data-ttu-id="6df42-284">Visualizzare l'elenco di utenti, ma includere solo il nome, se dispongono di una licenza e le due nuove proprietà che indicano se la loro cassetta postale è abilitata e se loro sono abilitati per Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span><span class="sxs-lookup"><span data-stu-id="6df42-284">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6df42-285">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6df42-285">See also</span></span>

[<span data-ttu-id="6df42-286">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df42-286">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6df42-287">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6df42-287">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6df42-288">Usare Windows PowerShell per creare report in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df42-288">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

