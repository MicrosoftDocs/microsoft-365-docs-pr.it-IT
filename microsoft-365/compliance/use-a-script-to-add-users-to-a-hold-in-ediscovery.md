---
title: Utilizzo di uno script per aggiungere gli utenti a un'esenzione in un caso di eDiscovery di base nel centro sicurezza & Compliance
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Informazioni su come eseguire uno script per aggiungere cassette postali & siti di OneDrive for business a un nuovo blocco associato a un caso di eDiscovery nel centro sicurezza & Compliance.
ms.openlocfilehash: 55ad3c8c8a4a6b77df4c2d3409fee6e5b43cc5f6
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391486"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="7d97f-103">Utilizzo di uno script per aggiungere gli utenti a un'esenzione in un caso di eDiscovery di base</span><span class="sxs-lookup"><span data-stu-id="7d97f-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="7d97f-104">Il Centro sicurezza & conformità fornisce i cmdlet di PowerShell che consentono di automatizzare le attività che richiedono tempo per la creazione e la gestione dei casi di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="7d97f-104">The Security & Compliance Center provides PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="7d97f-105">Attualmente, utilizzando lo strumento case di eDiscovery nel centro sicurezza & conformità per inserire un numero elevato di posizioni di contenuto del custode in attesa richiede tempo e preparazione.</span><span class="sxs-lookup"><span data-stu-id="7d97f-105">Currently, using the eDiscovery case tool in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="7d97f-106">Ad esempio, prima di creare un'esenzione, è necessario raccogliere l'URL per ogni sito di OneDrive for business che si desidera inserire in attesa.</span><span class="sxs-lookup"><span data-stu-id="7d97f-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="7d97f-107">Quindi, per ogni utente che si desidera inserire in attesa, è necessario aggiungere la propria cassetta postale e il proprio sito di OneDrive for business all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="7d97f-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="7d97f-108">Nelle versioni future del Centro sicurezza & conformità, questo sarà più facile da fare.</span><span class="sxs-lookup"><span data-stu-id="7d97f-108">In future releases of the Security & Compliance Center, this will get easier to do.</span></span> <span data-ttu-id="7d97f-109">Fino a quel momento, è possibile utilizzare lo script in questo articolo per automatizzare il processo.</span><span class="sxs-lookup"><span data-stu-id="7d97f-109">Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="7d97f-110">Lo script richiede il nome del dominio del sito personale dell'organizzazione, ad esempio **Contoso** nell'URL https://contoso-my.sharepoint.com) , il nome di un caso di eDiscovery esistente, il nome del nuovo blocco associato al caso, un elenco di indirizzi di posta elettronica degli utenti che si desidera conservare e una query di ricerca da utilizzare se si desidera creare un blocco basato su query.</span><span class="sxs-lookup"><span data-stu-id="7d97f-110">The script prompts you for the name of your organization's My Site domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="7d97f-111">Lo script ottiene quindi l'URL del sito di OneDrive for business per ogni utente nell'elenco, crea la nuova esenzione e quindi aggiunge la cassetta postale e il sito di OneDrive for business per ogni utente nell'elenco all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="7d97f-111">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="7d97f-112">Lo script genera anche file di registro che contengono informazioni sul nuovo blocco.</span><span class="sxs-lookup"><span data-stu-id="7d97f-112">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="7d97f-113">Di seguito vengono illustrati i passaggi per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="7d97f-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="7d97f-114">Passaggio 1: Installare SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="7d97f-114">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="7d97f-115">Passaggio 2: generazione di un elenco di utenti</span><span class="sxs-lookup"><span data-stu-id="7d97f-115">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="7d97f-116">Passaggio 3: eseguire lo script per creare un blocco e aggiungere utenti</span><span class="sxs-lookup"><span data-stu-id="7d97f-116">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="7d97f-117">Prima di aggiungere gli utenti a un'esenzione</span><span class="sxs-lookup"><span data-stu-id="7d97f-117">Before you add users to a hold</span></span>

- <span data-ttu-id="7d97f-118">Per eseguire lo script nel passaggio 3, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & compliance e amministratore di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7d97f-118">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="7d97f-119">Per ulteriori informazioni, vedere [assegnare le autorizzazioni di eDiscovery nel centro sicurezza & conformità di Office 365](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7d97f-119">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="7d97f-120">È possibile aggiungere un numero massimo di cassette postali di 1.000 e 100 siti a un blocco associato a un caso di eDiscovery nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="7d97f-120">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="7d97f-121">Presupponendo che tutti gli utenti che si desidera inserire in attesa dispongano di un sito di OneDrive for business, è possibile aggiungere un massimo di 100 utenti a un'esenzione utilizzando lo script in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="7d97f-121">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="7d97f-122">Assicurarsi di salvare l'elenco di utenti creato nel passaggio 2 e lo script nel passaggio 3 alla stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="7d97f-122">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="7d97f-123">Questo renderà più facile eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="7d97f-123">That will make it easier to run the script.</span></span>

- <span data-ttu-id="7d97f-124">Lo script aggiunge l'elenco di utenti a un nuovo blocco associato a un caso esistente.</span><span class="sxs-lookup"><span data-stu-id="7d97f-124">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="7d97f-125">Verificare che il caso in cui si desidera associare l'esenzione venga creato prima di eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="7d97f-125">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="7d97f-126">Ogni volta che si esegue lo script, vengono create nuove sessioni di PowerShell di sicurezza & conformità e di PowerShell di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7d97f-126">Each time you run the script, new Security & Compliance PowerShell and SharePoint Online PowerShell sessions are created.</span></span> <span data-ttu-id="7d97f-127">In questo modo, è possibile utilizzare tutte le sessioni di PowerShell disponibili.</span><span class="sxs-lookup"><span data-stu-id="7d97f-127">So you could use up all the PowerShell sessions available to you.</span></span> <span data-ttu-id="7d97f-128">Per evitare che ciò accada, è possibile eseguire i seguenti comandi per disconnettere le sessioni di PowerShell attive.</span><span class="sxs-lookup"><span data-stu-id="7d97f-128">To prevent this from happening, you can run the following commands to disconnect your active PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

   ```powershell
   Disconnect-SPOService
   ```

- <span data-ttu-id="7d97f-129">Lo script include la gestione degli errori minima.</span><span class="sxs-lookup"><span data-stu-id="7d97f-129">The script includes minimal error handling.</span></span> <span data-ttu-id="7d97f-130">Il suo scopo principale è quello di posizionare rapidamente e facilmente la cassetta postale e il sito di OneDrive for business di ogni utente in attesa.</span><span class="sxs-lookup"><span data-stu-id="7d97f-130">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="7d97f-p109">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="7d97f-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="7d97f-136">Passaggio 1: Installare SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="7d97f-136">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="7d97f-137">Il primo passaggio consiste nell'installare SharePoint Online Management Shell se non è già installato nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="7d97f-137">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="7d97f-138">Non è necessario utilizzare la shell in questa procedura, ma è necessario installarla perché contiene i prerequisiti richiesti dallo script eseguito nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="7d97f-138">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="7d97f-139">Questi prerequisiti consentono allo script di comunicare con SharePoint Online per ottenere gli URL per i siti di OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="7d97f-139">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="7d97f-140">Andare a [configurare l'ambiente di Windows PowerShell per SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkID=286318) ed eseguire il passaggio 1 e il passaggio 2 per installare SharePoint Online Management Shell nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="7d97f-140">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="7d97f-141">Passaggio 2: generazione di un elenco di utenti</span><span class="sxs-lookup"><span data-stu-id="7d97f-141">Step 2: Generate a list of users</span></span>

<span data-ttu-id="7d97f-142">Lo script nel passaggio 3 creerà un'esenzione associata a un caso di eDiscovery e i siti di aggiunta di cassette postali e OneDrive for business di un elenco di utenti all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="7d97f-142">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="7d97f-143">È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure eseguire un comando in Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file (che si trova nella stessa cartella in cui verrà salvato lo script nel passaggio 3).</span><span class="sxs-lookup"><span data-stu-id="7d97f-143">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="7d97f-144">Di seguito è riportato un comando di PowerShell (eseguito utilizzando Remote PowerShell connesso all'organizzazione di Exchange Online) per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="7d97f-144">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="7d97f-145">Dopo aver eseguito il comando, aprire il file di testo e rimuovere l'intestazione che contiene il nome della proprietà `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="7d97f-145">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="7d97f-146">Quindi rimuovere tutti gli indirizzi di posta elettronica ad eccezione di quelli per gli utenti che si desidera aggiungere al blocco che verrà creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="7d97f-146">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="7d97f-147">Verificare che non vi siano righe vuote prima o dopo l'elenco di indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="7d97f-147">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="7d97f-148">Passaggio 3: eseguire lo script per creare un blocco e aggiungere utenti</span><span class="sxs-lookup"><span data-stu-id="7d97f-148">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="7d97f-149">Quando si esegue lo script in questo passaggio, vengono richieste le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7d97f-149">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="7d97f-150">Assicurarsi di avere queste informazioni pronte prima di eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="7d97f-150">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="7d97f-151">**Credenziali utente:** Lo script utilizzerà le credenziali per connettersi al centro sicurezza & conformità con Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d97f-151">**Your user credentials:** The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="7d97f-152">Utilizzerà anche queste credenziali per accedere a SharePoint Online per ottenere gli URL di OneDrive for business per l'elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="7d97f-152">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="7d97f-153">**Nome del dominio del sito personale:** Il dominio del sito personale è il dominio che contiene tutti i siti di OneDrive for business nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7d97f-153">**Name of your My Site domain:** The My Site domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="7d97f-154">Ad esempio, se l'URL del dominio del sito personale è **https://contoso-my.sharepoint.com** , è necessario immettere `contoso` quando lo script richiede il nome del dominio del sito personale.</span><span class="sxs-lookup"><span data-stu-id="7d97f-154">For example, if the URL for your My Site domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your My Site domain.</span></span>

- <span data-ttu-id="7d97f-155">**Nome del caso:** Nome di un caso esistente.</span><span class="sxs-lookup"><span data-stu-id="7d97f-155">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="7d97f-156">Lo script creerà un nuovo blocco associato a questo caso.</span><span class="sxs-lookup"><span data-stu-id="7d97f-156">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="7d97f-157">**Nome dell'esenzione:** Il nome del blocco che lo script creerà e associerà al caso specificato.</span><span class="sxs-lookup"><span data-stu-id="7d97f-157">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="7d97f-158">**Query di ricerca per un blocco basato su query:** È possibile creare un blocco basato su query in modo che venga memorizzato solo il contenuto che soddisfa i criteri di ricerca specificati.</span><span class="sxs-lookup"><span data-stu-id="7d97f-158">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="7d97f-159">Per inserire tutto il contenuto in attesa, basta premere **invio** quando viene richiesto di eseguire una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="7d97f-159">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="7d97f-160">**Attivazione o meno dell'esenzione:** È possibile fare in modo che lo script venga attivato nell'esenzione dopo la creazione oppure che lo script possa creare il blocco senza abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="7d97f-160">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="7d97f-161">Se non è stato attivato lo script, è possibile attivarlo in un secondo momento nel centro sicurezza & Compliance oppure eseguendo i comandi di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d97f-161">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="7d97f-162">**Nome del file di testo con l'elenco di utenti** : il nome del file di testo del passaggio 2 che contiene l'elenco di utenti da aggiungere all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="7d97f-162">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="7d97f-163">Se il file si trova nella stessa cartella dello script, digitare il nome del file, ad esempio HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="7d97f-163">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="7d97f-164">Se il file di testo si trova in un'altra cartella, digitare il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="7d97f-164">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="7d97f-165">Dopo aver raccolto le informazioni che verranno richieste dallo script, il passaggio finale consiste nell'eseguire lo script per creare il nuovo blocco e aggiungervi gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7d97f-165">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="7d97f-166">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso del nome di file `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="7d97f-166">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="7d97f-167">Ad esempio, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="7d97f-167">For example, `AddUsersToHold.ps1`.</span></span>

   ```powershell
   #script begin
   " " 
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
   write-host "***********************************************"
   " " 
   # Get user credentials &amp; Connect to Office 365 SCC, SPO
   $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
   $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
   $a = Import-PSSession $s -AllowClobber
       if (!$s)
       {
           Write-Error "Couldn't create PowerShell session."
           return;
       }
   # Load the SharePoint assemblies from the SharePoint Online Management Shell
   # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
   if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
   {
       $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
       $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
       $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
       if (!$SharePointClient)
       {
           Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
           return;
       }
   }
   if (!$spCreds)
   {
       $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
   }
   # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
   ""
   $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
   ""
   # Get other required information
   do{
   $casename = Read-Host "Enter the name of the case"
   $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
   if($caseexists -ne 'True')
   {""
   write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
   ""}
   }While($caseexists -ne 'True')
   ""
   do{
   $holdName = Read-Host "Enter the name of the new hold"
   $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
   if($holdexists -eq 'True')
   {""
   write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
   ""}
   }While($holdexists -eq 'True')
   ""
   $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
   ""
   $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
   do{
   ""
   $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
   ""
   $fileexists = test-path -path $inputfile
   if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
   }while($fileexists -ne 'True')
   #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
       #in the list are unique.
     [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
     [int]$dupl = $emailAddresses.count
     [array]$emailAddresses = $emailAddresses | select-object -unique
     $dupl -= $emailAddresses.count
   #Validate email addresses so the hold creation does not run in to an error.
   if($emailaddresses.count -gt 0){
   write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
   ""
   Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
   ""
   $finallist =@()
   foreach($emailAddress in $emailAddresses)
   {
   if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
   {$finallist += $emailaddress}
   else {"Unable to find the user $emailaddress"
   [array]$excludedlist += $emailaddress}
   }
   ""
   #find user's OneDrive Site URL using email address
   Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
   ""
   $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
   $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
   # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
   $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
   $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False 
   $UserProfileService.Credentials = $credentials
   # Take care of auth cookies
   $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
   $uri = New-Object System.Uri($AdminUrl)
   $container = New-Object System.Net.CookieContainer
   $container.SetCookies($uri, $strAuthCookie)
   $UserProfileService.CookieContainer = $container
   $urls = @()
   foreach($emailAddress in $emailAddresses)
   {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
   }
   if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
   ""
   Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
   if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
   }
   else{
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
   }
   ""
   }
   else {"No valid locations were identified. Therefore, the hold wasn't created."}
   #write log files (if needed)
   $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
   $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
   if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
   {
   Write-Host "Generating output files..." -foregroundColor Yellow
   if($ODAdded.count -gt 0){
   "OneDrive Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
   if($ODExluded.count -gt 0){ 
   "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
   "================================" | add-content .\LocationsNotOnHold.txt
   $ODExluded | add-content .\LocationsNotOnHold.txt}
   if($finallist.count -gt 0){
   " " | add-content .\LocationsOnHold.txt
   "Exchange Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
   if($excludedlist.count -gt 0){
   " "| add-content .\LocationsNotOnHold.txt
   "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
   "===============================" | add-content .\LocationsNotOnHold.txt
   $excludedlist | add-content .\LocationsNotOnHold.txt}
   $FormatEnumerationLimit=-1
   if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
   if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
   }
   }
   else {"The hold wasn't created because no valid entries were found in the text file."}
   ""
   Write-host "Script complete!" -foregroundColor Yellow
   ""
   #script end
   ```

2. <span data-ttu-id="7d97f-168">Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="7d97f-168">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="7d97f-169">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="7d97f-169">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="7d97f-170">Immettere le informazioni richieste dallo script.</span><span class="sxs-lookup"><span data-stu-id="7d97f-170">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="7d97f-171">Lo script si connette a PowerShell per la sicurezza & Compliance Center e quindi crea la nuova conservazione nel caso di eDiscovery e aggiunge le cassette postali e OneDrive for business per gli utenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7d97f-171">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="7d97f-172">Per visualizzare il nuovo blocco, è possibile accedere al caso nella pagina **eDiscovery** del centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="7d97f-172">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span> 

<span data-ttu-id="7d97f-173">Al termine dell'esecuzione dello script, vengono creati i file di registro riportati di seguito e vengono salvati nella cartella in cui si trova lo script.</span><span class="sxs-lookup"><span data-stu-id="7d97f-173">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="7d97f-174">**LocationsOnHold.txt:** Contiene un elenco delle cassette postali e dei siti di OneDrive for business che lo script ha eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7d97f-174">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="7d97f-175">**LocationsNotOnHold.txt:** Contiene un elenco delle cassette postali e dei siti di OneDrive for business che lo script non ha posto in attesa.</span><span class="sxs-lookup"><span data-stu-id="7d97f-175">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="7d97f-176">Se un utente dispone di una cassetta postale, ma non di un sito di OneDrive for business, l'utente verrebbe incluso nell'elenco dei siti di OneDrive for business che non sono stati inseriti in attesa.</span><span class="sxs-lookup"><span data-stu-id="7d97f-176">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="7d97f-177">**GetCaseHoldPolicy.txt:** Contiene l'output del cmdlet **Get-CaseHoldPolicy** per il nuovo blocco, che lo script ha eseguito dopo la creazione del nuovo blocco.</span><span class="sxs-lookup"><span data-stu-id="7d97f-177">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="7d97f-178">Le informazioni restituite da questo cmdlet includono un elenco di utenti le cui cassette postali e i siti di OneDrive for business sono stati messi in attesa e se il blocco è abilitato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="7d97f-178">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="7d97f-179">**GetCaseHoldRule.txt:** Contiene l'output del cmdlet **Get-CaseHoldRule** per il nuovo blocco, che lo script ha eseguito dopo la creazione del nuovo blocco.</span><span class="sxs-lookup"><span data-stu-id="7d97f-179">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="7d97f-180">Le informazioni restituite da questo cmdlet includono la query di ricerca se è stato utilizzato lo script per creare un blocco basato su query.</span><span class="sxs-lookup"><span data-stu-id="7d97f-180">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
