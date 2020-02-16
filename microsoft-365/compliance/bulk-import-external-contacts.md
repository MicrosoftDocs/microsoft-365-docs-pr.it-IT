---
title: Importare in blocco i contatti esterni in Exchange Online
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
ms.openlocfilehash: c74e8932f7ed2feeca472848c88bdddbc740fe28
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078953"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="b6ba9-103">Importare in blocco i contatti esterni in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b6ba9-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="b6ba9-104">**Questo articolo è per gli amministratori. Si sta tentando di importare i contatti nella propria cassetta postale? Vedere [importare i contatti in Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="b6ba9-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="b6ba9-105">L'azienda dispone di un numero elevato di contatti aziendali esistenti che si desidera includere nella rubrica condivisa (denominato anche elenco indirizzi globale) in Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="b6ba9-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="b6ba9-106">Si desidera aggiungere contatti esterni come membri dei gruppi di distribuzione, proprio come è possibile con gli utenti all'interno dell'azienda?</span><span class="sxs-lookup"><span data-stu-id="b6ba9-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="b6ba9-107">In caso affermativo, è possibile utilizzare PowerShell di Exchange Online e un file CSV (con valori delimitati da virgole) per importare in blocco i contatti esterni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="b6ba9-108">Si tratta di un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="b6ba9-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="b6ba9-109">Passaggio 1: creare un file CSV contenente informazioni sui contatti esterni</span><span class="sxs-lookup"><span data-stu-id="b6ba9-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="b6ba9-110">Passaggio 2: creare i contatti esterni con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6ba9-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="b6ba9-111">Passaggio 3: aggiungere informazioni alle proprietà dei contatti esterni</span><span class="sxs-lookup"><span data-stu-id="b6ba9-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="b6ba9-112">Dopo aver completato questa procedura per importare i contatti, è possibile eseguire queste attività aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="b6ba9-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="b6ba9-113">Aggiungere altri contatti esterni</span><span class="sxs-lookup"><span data-stu-id="b6ba9-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="b6ba9-114">Nascondere i contatti esterni dalla rubrica condivisa</span><span class="sxs-lookup"><span data-stu-id="b6ba9-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="b6ba9-115">Passaggio 1: creare un file CSV contenente informazioni sui contatti esterni</span><span class="sxs-lookup"><span data-stu-id="b6ba9-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="b6ba9-116">Il primo passaggio consiste nel creare un file CSV che contiene informazioni su ogni contatto esterno che si desidera importare in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="b6ba9-117">Copiare il testo seguente in un file di testo in blocco note e salvarlo sul desktop come file CSV utilizzando un suffisso del nome file CSV. ad esempio, ExternalContacts. csv.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b6ba9-118">Se la lingua contiene caratteri speciali, ad esempio **å**, **ä**e **ö** in svedese, salvare il file CSV con UTF-8 o altra codifica Unicode quando si salva il file nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="b6ba9-119">La prima riga, o riga di intestazione, del file CSV elenca le proprietà dei contatti che è possibile utilizzare quando vengono importati in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="b6ba9-120">Ogni nome di proprietà è separato da una virgola.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="b6ba9-121">Ogni riga sotto la riga di intestazione rappresenta i valori delle proprietà per l'importazione di un singolo contatto esterno.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b6ba9-122">Questo testo include dati di esempio, che è possibile eliminare.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="b6ba9-123">Ma non eliminare o modificare la prima riga (intestazione).</span><span class="sxs-lookup"><span data-stu-id="b6ba9-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="b6ba9-124">Contiene tutte le proprietà dei contatti esterni.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="b6ba9-125">Aprire il file CSV in Microsoft Excel per modificare il file CSV, perché è molto più facile usare Excel per modificare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="b6ba9-126">Creare una riga per ogni contatto che si desidera importare in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="b6ba9-127">Inserire il numero di celle possibile.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="b6ba9-128">Queste informazioni vengono visualizzate nella rubrica condivisa per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="b6ba9-129">Le proprietà seguenti, che sono i primi quattro elementi della riga di intestazione, sono necessarie per creare un contatto esterno e devono essere inserite nel file CSV: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="b6ba9-130">Il comando di PowerShell eseguito nel passaggio 2 utilizzerà i valori per queste proprietà per creare i contatti.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="b6ba9-131">Passaggio 2: creare i contatti esterni con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6ba9-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="b6ba9-132">Il passaggio successivo consiste nell'utilizzare il file CSV creato nel passaggio 1 e PowerShell per importare in blocco i contatti esterni elencati nel file CSV in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="b6ba9-133">Connettere PowerShell all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="b6ba9-134">Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="b6ba9-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> <span data-ttu-id="b6ba9-135">Assicurarsi di utilizzare il nome utente e la password per l'account di amministratore globale di Office 365 quando ci si connette a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-135">Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="b6ba9-136">Dopo aver connesso PowerShell a Exchange Online, passare alla cartella desktop in cui è stato salvato il file CSV nel passaggio 1. ad esempio `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="b6ba9-137">Per creare i contatti esterni, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b6ba9-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="b6ba9-138">Potrebbe essere necessario un po' di tempo per creare i nuovi contatti, a seconda del numero di importazione.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="b6ba9-139">Al termine dell'esecuzione del comando, PowerShell Visualizza un elenco dei nuovi contatti che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="b6ba9-140">Per visualizzare i nuovi contatti esterni, accedere all'interfaccia di amministrazione di Exchange (EAC) e quindi fare clic su **destinatari** \> **contatti**.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b6ba9-141">Per istruzioni sulla connessione a EAC, vedere interfaccia di [amministrazione di Exchange in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span><span class="sxs-lookup"><span data-stu-id="b6ba9-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="b6ba9-142">Se necessario, fare clic su **Aggiorna** per aggiornare l'elenco e vedere i contatti esterni che sono stati importati.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="b6ba9-143">I contatti importati verranno visualizzati nella rubrica condivisa in Outlook e Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b6ba9-144">È inoltre possibile visualizzare i contatti nell'interfaccia di amministrazione di Microsoft 365 accedendo ai **contatti** **degli utenti** \> .</span><span class="sxs-lookup"><span data-stu-id="b6ba9-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="b6ba9-145">Passaggio 3: aggiungere informazioni alle proprietà dei contatti esterni</span><span class="sxs-lookup"><span data-stu-id="b6ba9-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="b6ba9-146">Dopo aver eseguito il comando nel passaggio 2, vengono creati i contatti esterni, ma non contengono alcuna informazione del contatto o dell'organizzazione, ovvero le informazioni provenienti dalla maggior parte delle celle nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="b6ba9-147">Ciò è dovuto al fatto che, quando si creano nuovi contatti esterni, vengono inserite solo le proprietà obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="b6ba9-148">Non si preoccupi se non si dispone di tutte le informazioni inserite nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="b6ba9-149">Se non è presente, non verrà aggiunta.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="b6ba9-150">Connettere PowerShell all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="b6ba9-151">Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="b6ba9-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="b6ba9-152">Passare alla cartella desktop in cui è stato salvato il file CSV nel passaggio 1. ad esempio, `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="b6ba9-153">Eseguire i due comandi seguenti per aggiungere le altre proprietà dal file CSV ai contatti esterni creati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="b6ba9-154">Il parametro _Manager_ potrebbe essere problematico.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="b6ba9-155">Se la cella è vuota nel file CSV, verrà visualizzato un messaggio di errore e nessuna delle informazioni sulle proprietà verrà aggiunta al contatto.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="b6ba9-156">Se non è necessario specificare un Manager, è sufficiente eliminare ` -Manager $_.Manager ` il comando PowerShell precedente.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="b6ba9-157">Anche in questo caso, potrebbe essere necessario un po' di tempo per aggiornare i contatti, a seconda del numero di importati nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="b6ba9-158">Per verificare che le proprietà siano state aggiunte ai contatti:</span><span class="sxs-lookup"><span data-stu-id="b6ba9-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="b6ba9-159">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="b6ba9-160">Fare clic su un contatto e \*\*\*\* ![quindi fare clic](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) su Modifica icona modifica per visualizzare le proprietà del contatto.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="b6ba9-161">È tutto.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-161">That's it!</span></span> <span data-ttu-id="b6ba9-162">Gli utenti possono visualizzare i contatti e le informazioni aggiuntive nella Rubrica Outlook e Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="b6ba9-163">Aggiungere altri contatti esterni</span><span class="sxs-lookup"><span data-stu-id="b6ba9-163">Add more external contacts</span></span>

<span data-ttu-id="b6ba9-164">È possibile ripetere i passaggi da 1 a passaggio 3 per aggiungere nuovi contatti esterni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="b6ba9-165">L'utente o gli utenti dell'azienda possono semplicemente aggiungere una nuova riga nel file CSV per il nuovo contatto.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="b6ba9-166">È quindi possibile eseguire i comandi di PowerShell del passaggio 2 e del passaggio 3 per creare e aggiungere informazioni ai nuovi contatti.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6ba9-167">Quando si esegue il comando per creare nuovi contatti, è possibile che venga visualizzato un messaggio di errore che indica che i contatti creati precedentemente sono già esistenti.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="b6ba9-168">Tuttavia, viene creato un nuovo contatto aggiunto al file CSV.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="b6ba9-169">Nascondere i contatti esterni dalla rubrica condivisa></span><span class="sxs-lookup"><span data-stu-id="b6ba9-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="b6ba9-170">Alcune aziende possono utilizzare i contatti esterni solo in modo che possano essere aggiunti come membri dei gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="b6ba9-171">In questo scenario, è possibile che si desideri nascondere i contatti esterni dalla rubrica condivisa.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="b6ba9-172">Ecco come:</span><span class="sxs-lookup"><span data-stu-id="b6ba9-172">Here's how:</span></span>
  
1.  <span data-ttu-id="b6ba9-173">Connettere PowerShell all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="b6ba9-174">Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="b6ba9-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="b6ba9-175">Per nascondere un singolo contatto esterno, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="b6ba9-176">Ad esempio, per nascondere Pilar Pinilla dalla rubrica condivisa, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b6ba9-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="b6ba9-177">Per nascondere tutti i contatti esterni dalla rubrica condivisa, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b6ba9-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="b6ba9-178">Dopo averli nascosti, i contatti esterni non vengono visualizzati nella rubrica condivisa, ma è comunque possibile aggiungerli come membri di un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b6ba9-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
