---
title: Utilizzare uno script per aggiungere utenti a un'esenzione in un caso di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Informazioni su come eseguire uno script per aggiungere cassette postali & siti di OneDrive for Business a un nuovo blocco associato a un caso di eDiscovery nel Centro conformità Microsoft 365.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909916"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="e8e6f-103">Utilizzare uno script per aggiungere utenti a un'esenzione in un caso di eDiscovery di base</span><span class="sxs-lookup"><span data-stu-id="e8e6f-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="e8e6f-104">Security & Compliance Center PowerShell fornisce cmdlet che consentono di automatizzare le attività che richiedono molto tempo relative alla creazione e alla gestione dei casi di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="e8e6f-105">Attualmente, l'utilizzo del caso Core eDiscovery nel Centro sicurezza & conformità per mettere in attesa un numero elevato di posizioni di contenuto depositario richiede tempo e preparazione.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="e8e6f-106">Ad esempio, prima di creare un'esenzione, è necessario raccogliere l'URL per ogni sito di OneDrive for Business che si desidera mettere in attesa.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="e8e6f-107">Quindi, per ogni utente che si desidera mettere in attesa, è necessario aggiungere la propria cassetta postale e il sito di OneDrive for Business all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="e8e6f-108">È possibile utilizzare lo script in questo articolo per automatizzare questo processo.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="e8e6f-109">Lo script richiede il nome del dominio del sito personale dell'organizzazione( ad esempio, nell'URL , il nome di un caso eDiscovery esistente, il nome del nuovo blocco associato al caso, un elenco di indirizzi di posta elettronica degli utenti che si desidera mettere in attesa e una query di ricerca da utilizzare se si desidera creare un blocco basato su `contoso` https://contoso-my.sharepoint.com) query.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="e8e6f-110">Lo script ottiene quindi l'URL per il sito di OneDrive for Business per ogni utente nell'elenco, crea il nuovo blocco e quindi aggiunge la cassetta postale e il sito di OneDrive for Business per ogni utente nell'elenco all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="e8e6f-111">Lo script genera inoltre file di registro contenenti informazioni sulla nuova esenzione.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="e8e6f-112">Ecco i passaggi per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="e8e6f-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="e8e6f-113">Passaggio 1: Installare SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e8e6f-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="e8e6f-114">Passaggio 2: Generare un elenco di utenti</span><span class="sxs-lookup"><span data-stu-id="e8e6f-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="e8e6f-115">Passaggio 3: Eseguire lo script per creare un'esenzione e aggiungere utenti</span><span class="sxs-lookup"><span data-stu-id="e8e6f-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="e8e6f-116">Prima di aggiungere utenti a un'esenzione</span><span class="sxs-lookup"><span data-stu-id="e8e6f-116">Before you add users to a hold</span></span>

- <span data-ttu-id="e8e6f-117">Per eseguire lo script nel passaggio 3, è necessario essere membri del gruppo di ruoli Responsabile eDiscovery nel Centro sicurezza & conformità e un amministratore di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="e8e6f-118">Per ulteriori informazioni, vedere [Assign eDiscovery permissions in the Office 365 Security & Compliance Center.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="e8e6f-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="e8e6f-119">È possibile aggiungere un massimo di 1.000 cassette postali e 100 siti a un blocco associato a un caso di eDiscovery nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="e8e6f-120">Presupponendo che ogni utente che si desidera mettere in attesa abbia un sito di OneDrive for Business, è possibile aggiungere un massimo di 100 utenti a un'esenzione utilizzando lo script in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="e8e6f-121">Assicurarsi di salvare l'elenco degli utenti creati nel passaggio 2 e lo script nel passaggio 3 nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="e8e6f-122">In questo modo sarà più semplice eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="e8e6f-123">Lo script aggiunge l'elenco di utenti a una nuova esenzione associata a un caso esistente.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="e8e6f-124">Assicurarsi che il caso a cui si desidera associare l'esenzione venga creato prima di eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="e8e6f-125">Lo script in questo articolo supporta l'autenticazione moderna quando ci si connette a PowerShell & Centro conformità e SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="e8e6f-126">È possibile utilizzare lo script così come è se si è un'organizzazione Microsoft 365 o Microsoft 365 GCC.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="e8e6f-127">Se si è un'organizzazione di Office 365 Germany, un'organizzazione Microsoft 365 GCC High o un'organizzazione DoD di Microsoft 365, sarà necessario modificare lo script per eseguirlo correttamente.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="e8e6f-128">In particolare, è necessario modificare la riga e utilizzare i parametri `Connect-IPPSSession` *ConnectionUri* e *AzureADAuthorizationEndpointUri* (e i valori appropriati per il tipo di organizzazione) per connettersi a PowerShell del Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="e8e6f-129">Per ulteriori informazioni, vedere gli esempi in [Connect to Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)</span><span class="sxs-lookup"><span data-stu-id="e8e6f-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="e8e6f-130">Lo script si disconnette automaticamente da PowerShell & Centro sicurezza e conformità e SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="e8e6f-131">Lo script include una gestione minima degli errori.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-131">The script includes minimal error handling.</span></span> <span data-ttu-id="e8e6f-132">Lo scopo principale è quello di mettere in attesa la cassetta postale e il sito OneDrive for Business di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="e8e6f-p109">Gli script di esempio forniti in questo articolo non sono supportati da alcun programma o servizio standard di supporto Microsoft. Gli script di esempio sono forniti così come sono senza alcun tipo di garanzia. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. Qualsiasi rischio eventuale pervenga, durante l'utilizzo degli script di esempio e della documentazione, si intende a carico dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script è da ritenersi responsabile per qualsiasi danno eventuale (inclusi, senza limitazione alcuna, danni riguardanti profitti aziendali, interruzione di attività, perdita di informazioni aziendali o altra perdita pecuniaria) derivanti dall'utilizzo o dall'incapacità di utilizzo degli script di esempio e della documentazione, anche nel caso in cui Microsoft sia stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="e8e6f-138">Passaggio 1: Installare SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e8e6f-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="e8e6f-139">Il primo passaggio consiste nell'installare SharePoint Online Management Shell se non è già installato nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="e8e6f-140">Non è necessario utilizzare la shell in questa procedura, ma è necessario installarla perché contiene i prerequisiti richiesti dallo script eseguito nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="e8e6f-141">Questi prerequisiti consentono allo script di comunicare con SharePoint Online per ottenere gli URL per i siti di OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="e8e6f-142">Passare a [Configurare SharePoint Online Management Shell Windows PowerShell ambiente](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire i passaggi 1 e 2 per installare SharePoint Online Management Shell nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="e8e6f-143">Passaggio 2: Generare un elenco di utenti</span><span class="sxs-lookup"><span data-stu-id="e8e6f-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="e8e6f-144">Lo script nel passaggio 3 creerà un'esenzione associata a un caso di eDiscovery e aggiungerà le cassette postali e i siti di OneDrive for Business di un elenco di utenti al blocco.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="e8e6f-145">È possibile digitare gli indirizzi di posta elettronica in un file di testo oppure eseguire un comando in Windows PowerShell per ottenere un elenco di indirizzi di posta elettronica e salvarli in un file ,che si trova nella stessa cartella in cui verrà salvato lo script nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="e8e6f-146">Ecco un comando di PowerShell (eseguito utilizzando PowerShell remoto connesso all'organizzazione di Exchange Online) per ottenere un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione e salvarlo in un file di testo denominato HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="e8e6f-147">Dopo aver eseguito questo comando, aprire il file di testo e rimuovere l'intestazione contenente il nome della proprietà,  `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="e8e6f-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="e8e6f-148">Rimuovere quindi tutti gli indirizzi di posta elettronica ad eccezione di quelli per gli utenti che si desidera aggiungere all'esenzione che si creerà nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="e8e6f-149">Verificare che non siano presenti righe vuote prima o dopo l'elenco degli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="e8e6f-150">Passaggio 3: Eseguire lo script per creare un'esenzione e aggiungere utenti</span><span class="sxs-lookup"><span data-stu-id="e8e6f-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="e8e6f-151">Quando si esegue lo script in questo passaggio, verranno richieste le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="e8e6f-152">Assicurarsi di avere queste informazioni pronte prima di eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="e8e6f-153">**Credenziali utente:** Lo script userà le credenziali per connettersi al Centro sicurezza & conformità con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-153">**Your user credentials:** The script will use your credentials to connect to Security & Compliance Center with PowerShell.</span></span> <span data-ttu-id="e8e6f-154">Userà anche queste credenziali per accedere a SharePoint Online per ottenere gli URL di OneDrive for Business per l'elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="e8e6f-155">**Nome del dominio di SharePoint:** Lo script richiede di immettere questo nome in modo che possa connettersi all'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-155">**Name of your SharePoint domain:** The script prompts you to enter this name so it can connect to the SharePoint admin center.</span></span> <span data-ttu-id="e8e6f-156">Usa anche il nome di dominio per gli URL di OneDrive nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-156">It also uses the domain name for the OneDrive URLs in your organization.</span></span> <span data-ttu-id="e8e6f-157">Ad esempio, se l'URL dell'interfaccia di amministrazione è e l'URL per OneDrive è , immettere quando lo script richiede il `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` nome di `contoso` dominio.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-157">For example, if the URL for your admin center is `https://contoso-admin.sharepoint.com` and the URL for OneDrive is `https://contoso-my.sharepoint.com`, then you would enter `contoso` when the script prompts you for your domain name.</span></span>

- <span data-ttu-id="e8e6f-158">**Nome del caso:** Nome di un caso esistente.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-158">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="e8e6f-159">Lo script creerà una nuova esenzione associata a questo caso.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-159">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="e8e6f-160">**Nome del blocco:** Nome del blocco che verrà creato e associato al caso specificato.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-160">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="e8e6f-161">**Query di ricerca per un blocco basato su query:** È possibile creare un'esenzione basata su query in modo che solo il contenuto che soddisfa i criteri di ricerca specificati sia messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-161">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="e8e6f-162">Per mettere tutto il contenuto in attesa, è sufficiente premere **INVIO** quando viene richiesta una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-162">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="e8e6f-163">**Attivare o meno l'esenzione:** È possibile fare in modo che lo script accerti l'esenzione dopo la creazione oppure che lo script crei l'esenzione senza abilitarla.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-163">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="e8e6f-164">Se lo script non attiva l'esenzione, è possibile attivarlo in un secondo momento nel Centro sicurezza & conformità o eseguendo i comandi di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8e6f-164">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="e8e6f-165">**Nome del file di testo con l'elenco** di utenti - Nome del file di testo del passaggio 2 contenente l'elenco di utenti da aggiungere all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-165">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="e8e6f-166">Se il file si trova nella stessa cartella dello script, è sufficiente digitare il nome del file, ad esempio HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-166">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="e8e6f-167">Se il file di testo si trova in un'altra cartella, digitare il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-167">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="e8e6f-168">Dopo aver raccolto le informazioni richieste nello script, il passaggio finale consiste nell'eseguire lo script per creare il nuovo blocco e aggiungervi utenti.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-168">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="e8e6f-169">Salvare il testo seguente in un Windows PowerShell di script utilizzando un suffisso di nome file di `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e8e6f-169">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="e8e6f-170">Ad esempio, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-170">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="e8e6f-171">Nel computer locale, aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-171">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="e8e6f-172">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="e8e6f-172">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="e8e6f-173">Immettere le informazioni richieste per lo script.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-173">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="e8e6f-174">Lo script si connette & PowerShell del Centro sicurezza e conformità e quindi crea il nuovo blocco nel caso di eDiscovery e aggiunge le cassette postali e OneDrive for Business per gli utenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-174">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="e8e6f-175">È possibile passare al caso nella pagina **eDiscovery** nel Centro sicurezza & conformità per visualizzare il nuovo blocco.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-175">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="e8e6f-176">Al termine dell'esecuzione, lo script crea i file di registro seguenti e li salva nella cartella in cui si trova lo script.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-176">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="e8e6f-177">**LocationsOnHold.txt:** Contiene un elenco delle cassette postali e dei siti di OneDrive for Business che lo script ha correttamente messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-177">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="e8e6f-178">**LocationsNotOnHold.txt:** Contiene un elenco di cassette postali e siti di OneDrive for Business che lo script non ha posto in attesa.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-178">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="e8e6f-179">Se un utente dispone di una cassetta postale, ma non di un sito di OneDrive for Business, l'utente verrà incluso nell'elenco dei siti di OneDrive for Business che non sono stati messi in attesa.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-179">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="e8e6f-180">**GetCaseHoldPolicy.txt:** Contiene l'output del cmdlet **Get-CaseHoldPolicy** per il nuovo blocco, eseguito dopo la creazione del nuovo blocco.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-180">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="e8e6f-181">Le informazioni restituite da questo cmdlet includono un elenco di utenti le cui cassette postali e i siti di OneDrive for Business sono stati messi in attesa e se il blocco è abilitato o disabilitato.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-181">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="e8e6f-182">**GetCaseHoldRule.txt:** Contiene l'output del cmdlet **Get-CaseHoldRule** per il nuovo blocco, eseguito dopo la creazione del nuovo blocco.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-182">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="e8e6f-183">Le informazioni restituite da questo cmdlet includono la query di ricerca se è stato utilizzato lo script per creare un'esenzione basata su query.</span><span class="sxs-lookup"><span data-stu-id="e8e6f-183">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>