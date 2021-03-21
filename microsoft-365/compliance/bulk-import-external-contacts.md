---
title: Importazione in blocco dei contatti esterni in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Informazioni su come gli amministratori possono utilizzare PowerShell di Exchange Online e un file CSV per importare in blocco i contatti esterni nell'elenco indirizzi globale.
ms.openlocfilehash: 178e3676f8dc5fb59cdad9cc46d7ecbd9dddb90e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918212"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="781e5-103">Importazione in blocco dei contatti esterni in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="781e5-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="781e5-104">**Questo articolo è per gli amministratori. Si sta tentando di importare i contatti nella propria cassetta postale? Vedere [Importare contatti in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="781e5-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="781e5-105">L'azienda dispone di molti contatti commerciali esistenti che si desidera includere nella rubrica condivisa (denominata anche elenco indirizzi globale) in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="781e5-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="781e5-106">Si desidera aggiungere contatti esterni come membri dei gruppi di distribuzione, proprio come con gli utenti all'interno dell'azienda?</span><span class="sxs-lookup"><span data-stu-id="781e5-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="781e5-107">In tal caso, è possibile utilizzare PowerShell di Exchange Online e un file CSV (con valori delimitati da virgole) per importare in blocco i contatti esterni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="781e5-108">Si tratta di un processo in tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="781e5-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="781e5-109">Passaggio 1: Creare un file CSV contenente informazioni sui contatti esterni</span><span class="sxs-lookup"><span data-stu-id="781e5-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="781e5-110">Passaggio 2: Creare i contatti esterni con PowerShell</span><span class="sxs-lookup"><span data-stu-id="781e5-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="781e5-111">Passaggio 3: Aggiungere informazioni alle proprietà dei contatti esterni</span><span class="sxs-lookup"><span data-stu-id="781e5-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="781e5-112">Dopo aver completato questi passaggi per importare i contatti, è possibile eseguire queste attività aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="781e5-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="781e5-113">Aggiungere altri contatti esterni</span><span class="sxs-lookup"><span data-stu-id="781e5-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="781e5-114">Nascondere i contatti esterni dalla rubrica condivisa</span><span class="sxs-lookup"><span data-stu-id="781e5-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="781e5-115">Passaggio 1: Creare un file CSV contenente informazioni sui contatti esterni</span><span class="sxs-lookup"><span data-stu-id="781e5-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="781e5-116">Il primo passaggio consiste nel creare un file CSV contenente informazioni su ogni contatto esterno che si desidera importare in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="781e5-117">Copiare il testo seguente in un file di testo in NotePad e salvarlo sul desktop come file CSV utilizzando il suffisso del nome file csv; ad esempio, ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="781e5-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="781e5-118">Se la lingua contiene caratteri speciali ,ad esempio **å,** **ä** e **ö** in svedese, salvare il file CSV con UTF-8 o un'altra codifica Unicode quando si salva il file in NotePad.</span><span class="sxs-lookup"><span data-stu-id="781e5-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="781e5-119">Nella prima riga, o riga di intestazione, del file CSV sono elencate le proprietà dei contatti che possono essere utilizzate quando vengono importati in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="781e5-120">Ogni nome di proprietà è separato da una virgola.</span><span class="sxs-lookup"><span data-stu-id="781e5-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="781e5-121">Ogni riga sotto la riga di intestazione rappresenta i valori delle proprietà per l'importazione di un singolo contatto esterno.</span><span class="sxs-lookup"><span data-stu-id="781e5-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="781e5-122">Questo testo include dati di esempio che è possibile eliminare.</span><span class="sxs-lookup"><span data-stu-id="781e5-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="781e5-123">Non eliminare o modificare la prima riga (intestazione).</span><span class="sxs-lookup"><span data-stu-id="781e5-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="781e5-124">Contiene tutte le proprietà per i contatti esterni.</span><span class="sxs-lookup"><span data-stu-id="781e5-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="781e5-125">Aprire il file CSV in Microsoft Excel per modificare il file CSV perché è molto più semplice utilizzare Excel per modificare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="781e5-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="781e5-126">Creare una riga per ogni contatto che si desidera importare in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="781e5-127">Popolare il maggior numero possibile di celle.</span><span class="sxs-lookup"><span data-stu-id="781e5-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="781e5-128">Queste informazioni verranno visualizzate nella rubrica condivisa per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="781e5-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="781e5-129">Per creare un contatto esterno, sono necessarie le proprietà seguenti, ovvero i primi quattro elementi della riga di intestazione, che devono essere popolate nel file CSV: **ExternalEmailAddress,** **Name,** **FirstName,** **LastName.**</span><span class="sxs-lookup"><span data-stu-id="781e5-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="781e5-130">Il comando di PowerShell eseguito nel passaggio 2 utilizzerà i valori per queste proprietà per creare i contatti.</span><span class="sxs-lookup"><span data-stu-id="781e5-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="781e5-131">Passaggio 2: Creare i contatti esterni con PowerShell</span><span class="sxs-lookup"><span data-stu-id="781e5-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="781e5-132">Il passaggio successivo consiste nell'usare il file CSV creato nel passaggio 1 e PowerShell per importare in blocco i contatti esterni elencati nel file CSV in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="781e5-133">Connettere PowerShell all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="781e5-134">Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="781e5-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="781e5-135">Assicurarsi di utilizzare il nome utente e la password per l'account amministratore globale quando ci si connette a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="781e5-136">Dopo aver connesso PowerShell a Exchange Online, passare alla cartella desktop in cui è stato salvato il file CSV nel passaggio 1; ad esempio `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="781e5-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="781e5-137">Eseguire il comando seguente per creare i contatti esterni:</span><span class="sxs-lookup"><span data-stu-id="781e5-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="781e5-138">La creazione dei nuovi contatti potrebbe richiedere alcuni minuti, a seconda del numero di contatti da importare.</span><span class="sxs-lookup"><span data-stu-id="781e5-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="781e5-139">Al termine dell'esecuzione del comando, PowerShell visualizza un elenco dei nuovi contatti creati.</span><span class="sxs-lookup"><span data-stu-id="781e5-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="781e5-140">Per visualizzare i nuovi contatti esterni, passare all'interfaccia di amministrazione di Exchange (EAC), quindi fare clic su **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="781e5-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="781e5-141">Per istruzioni sulla connessione all'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="781e5-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span> 
  
5. <span data-ttu-id="781e5-142">Se necessario, fare **clic su Aggiorna** per aggiornare l'elenco e visualizzare i contatti esterni importati.</span><span class="sxs-lookup"><span data-stu-id="781e5-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="781e5-143">I contatti importati verranno visualizzati nella rubrica condivisa in Outlook e Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="781e5-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="781e5-144">È inoltre possibile visualizzare i contatti nell'interfaccia di amministrazione di Microsoft 365 andando a **Utenti** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="781e5-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="781e5-145">Passaggio 3: Aggiungere informazioni alle proprietà dei contatti esterni</span><span class="sxs-lookup"><span data-stu-id="781e5-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="781e5-146">Dopo aver eseguito il comando nel passaggio 2, i contatti esterni vengono creati, ma non contengono informazioni sul contatto o sull'organizzazione, ovvero le informazioni della maggior parte delle celle del file CSV.</span><span class="sxs-lookup"><span data-stu-id="781e5-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="781e5-147">Questo perché quando si creano nuovi contatti esterni, vengono popolate solo le proprietà necessarie.</span><span class="sxs-lookup"><span data-stu-id="781e5-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="781e5-148">Non preoccuparti se non hai tutte le informazioni inserite nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="781e5-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="781e5-149">Se non è presente, non verrà aggiunto.</span><span class="sxs-lookup"><span data-stu-id="781e5-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="781e5-150">Connettere PowerShell all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="781e5-151">Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="781e5-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="781e5-152">Passare alla cartella desktop in cui è stato salvato il file CSV nel passaggio 1. ad `C:\Users\Administrator\desktop` esempio.</span><span class="sxs-lookup"><span data-stu-id="781e5-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="781e5-153">Eseguire i due comandi seguenti per aggiungere le altre proprietà dal file CSV ai contatti esterni creati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="781e5-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="781e5-154">Il  _parametro Manager_ potrebbe essere problematico.</span><span class="sxs-lookup"><span data-stu-id="781e5-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="781e5-155">Se la cella è vuota nel file CSV, verrà visualizzato un errore e nessuna delle informazioni sulle proprietà verrà aggiunta al contatto.</span><span class="sxs-lookup"><span data-stu-id="781e5-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="781e5-156">Se non è necessario specificare un manager, è sufficiente eliminare  ` -Manager $_.Manager ` dal comando powershell precedente.</span><span class="sxs-lookup"><span data-stu-id="781e5-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="781e5-157">Anche in questo caso, l'aggiornamento dei contatti potrebbe richiedere alcuni minuti, a seconda del numero di contatti importati nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="781e5-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="781e5-158">Per verificare che le proprietà siano state aggiunte ai contatti:</span><span class="sxs-lookup"><span data-stu-id="781e5-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="781e5-159">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="781e5-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="781e5-160">Fare clic su un contatto e quindi **su Modifica** icona Modifica per visualizzare le proprietà ![ del ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) contatto.</span><span class="sxs-lookup"><span data-stu-id="781e5-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="781e5-161">È tutto.</span><span class="sxs-lookup"><span data-stu-id="781e5-161">That's it!</span></span> <span data-ttu-id="781e5-162">Gli utenti possono visualizzare i contatti e le informazioni aggiuntive nella rubrica Outlook e Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="781e5-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="781e5-163">Aggiungere altri contatti esterni</span><span class="sxs-lookup"><span data-stu-id="781e5-163">Add more external contacts</span></span>

<span data-ttu-id="781e5-164">È possibile ripetere i passaggi da 1 a 3 per aggiungere nuovi contatti esterni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="781e5-165">L'utente o gli utenti della società possono semplicemente aggiungere una nuova riga nel file CSV per il nuovo contatto.</span><span class="sxs-lookup"><span data-stu-id="781e5-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="781e5-166">È quindi possibile eseguire i comandi di PowerShell dai passaggi 2 e 3 per creare e aggiungere informazioni ai nuovi contatti.</span><span class="sxs-lookup"><span data-stu-id="781e5-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="781e5-167">Quando si esegue il comando per creare nuovi contatti, è possibile che venga visualizzato un errore che indica che i contatti creati in precedenza esistono già.</span><span class="sxs-lookup"><span data-stu-id="781e5-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="781e5-168">Tuttavia, viene creato qualsiasi nuovo contatto aggiunto al file CSV.</span><span class="sxs-lookup"><span data-stu-id="781e5-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="781e5-169">Nascondere i contatti esterni dalla rubrica condivisa></span><span class="sxs-lookup"><span data-stu-id="781e5-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="781e5-170">Alcune società possono utilizzare solo contatti esterni in modo che possano essere aggiunti come membri dei gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="781e5-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="781e5-171">In questo scenario, potrebbe essere necessario nascondere i contatti esterni dalla rubrica condivisa.</span><span class="sxs-lookup"><span data-stu-id="781e5-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="781e5-172">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="781e5-172">Here's how:</span></span>
  
1.  <span data-ttu-id="781e5-173">Connettere PowerShell all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="781e5-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="781e5-174">Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="781e5-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="781e5-175">Per nascondere un singolo contatto esterno, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="781e5-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="781e5-176">Ad esempio, per nascondere Pilar Pinilla dalla rubrica condivisa, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="781e5-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="781e5-177">Per nascondere tutti i contatti esterni dalla rubrica condivisa, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="781e5-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="781e5-178">Dopo averli nascosti, i contatti esterni non vengono visualizzati nella rubrica condivisa, ma è comunque possibile aggiungerli come membri di un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="781e5-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>