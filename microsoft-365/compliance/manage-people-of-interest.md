---
title: Gestire gli utenti che interessano le indagini sui dati (anteprima)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come gestire gli utenti interessati all'ambito della ricerca o alla visualizzazione di dati quali i registri dei contatti, delle posizioni e delle attività.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7cab1904731f325f1ec45685ddf122e5ee375a2b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036069"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a><span data-ttu-id="927ac-103">Gestire gli utenti che interessano le indagini sui dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="927ac-103">Manage people of interest in Data Investigations (Preview)</span></span>

<span data-ttu-id="927ac-104">Le indagini sui dati coinvolgono spesso persone di interesse.</span><span class="sxs-lookup"><span data-stu-id="927ac-104">Data investigations often involve people of interest.</span></span> <span data-ttu-id="927ac-105">In genere, si tratta di persone proprietarie dei dati non posizionati, sensibili o dannosi che si sta indagando o che si desidera correggere.</span><span class="sxs-lookup"><span data-stu-id="927ac-105">Usually they are people who own the misplaced, sensitive or malicious data that you're investigating or looking to remediate.</span></span> <span data-ttu-id="927ac-106">In **indagini sui dati (Preview)**, è possibile aggiungerli per individuare le origini dati da utilizzare nell'ambito della ricerca o per visualizzare informazioni aggiuntive, ad esempio i registri contatti, percorso e attività.</span><span class="sxs-lookup"><span data-stu-id="927ac-106">In **Data Investigations (Preview)**, you can add them to discover their data sources to use in scoping your search or view additional information such as contact, location and activity logs.</span></span> 


## <a name="add-people-of-interest"></a><span data-ttu-id="927ac-107">Aggiungere persone di interesse</span><span class="sxs-lookup"><span data-stu-id="927ac-107">Add people of interest</span></span>

<span data-ttu-id="927ac-108">Nella scheda **utenti di interesse** è possibile aggiungere persone di interesse e individuare le origini dati, ad esempio le cassette postali di Exchange o il sito di OneDrive for business, che è possibile utilizzare per l'ambito della ricerca.</span><span class="sxs-lookup"><span data-stu-id="927ac-108">In **People of interest** tab, you can add people of interest and discover their data sources such as Exchange mailboxes or OneDrive for Business site that you can use to scope your search.</span></span> <span data-ttu-id="927ac-109">Quando gli utenti sono interessati, le ricerche sono più performanti e accurate perché lo strumento rielabora tutti i dati non indicizzati, ad esempio immagini o tipi di file non supportati.</span><span class="sxs-lookup"><span data-stu-id="927ac-109">When scoped down by people of interest, searches are more performant and accurate because the tool re-processes any unindexed data such as images or unsupported file types.</span></span> <span data-ttu-id="927ac-110">È inoltre possibile visualizzare le informazioni di contatto, le informazioni sulla posizione e i registri delle attività che è possibile utilizzare per avviare le comunicazioni o approfondire le proprie attività.</span><span class="sxs-lookup"><span data-stu-id="927ac-110">You can also see their contact information, location information and activity logs that you can use to initiate communications or further investigate their activities.</span></span> 

<span data-ttu-id="927ac-111">Per aggiungere persone di interesse a un'indagine:</span><span class="sxs-lookup"><span data-stu-id="927ac-111">To add people of interest to an investigation:</span></span>

1. <span data-ttu-id="927ac-112">Dalla pagina **indagini dati (anteprima)** , andare all'inchiesta.</span><span class="sxs-lookup"><span data-stu-id="927ac-112">From the **Data Investigations (Preview)** page, go to your investigation.</span></span>
 
2. <span data-ttu-id="927ac-113">Dopo aver selezionato un'indagine, passare alla scheda **persone interessate** e fare clic su **+ Aggiungi persone di interesse**.</span><span class="sxs-lookup"><span data-stu-id="927ac-113">After you have selected a investigation, go to the **People of interest** tab and click **+ Add people of interest**.</span></span> 
 
3. <span data-ttu-id="927ac-114">Scegliere gli utenti che si desidera aggiungere all'indagine.</span><span class="sxs-lookup"><span data-stu-id="927ac-114">Choose people that you want to add to the investigation.</span></span> <span data-ttu-id="927ac-115">È possibile iniziare digitando la ricerca e selezionando gli utenti dall'Azure Active Directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="927ac-115">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="927ac-116">Dopo aver completato l'elenco di persone di interesse, fare clic su **Avanti** per mappare le origini dati.</span><span class="sxs-lookup"><span data-stu-id="927ac-116">After you have finalized the list of people of interest, click **Next** to map their data sources.</span></span> 

5. <span data-ttu-id="927ac-117">Optional Per ogni persona, selezionare **Exchange** per aggiungere la cassetta postale di Exchange principale della persona e **OneDrive** per aggiungere il sito principale di OneDrive for business della persona.</span><span class="sxs-lookup"><span data-stu-id="927ac-117">[Optional] For each person, select **Exchange** to add person's primary Exchange mailbox, and **OneDrive** to add person's primary OneDrive for Business site.</span></span>

6. <span data-ttu-id="927ac-118">Optional Fare clic su **Avanti** per aggiungere eventuali origini dati aggiuntive che si desidera associare ai propri utenti.</span><span class="sxs-lookup"><span data-stu-id="927ac-118">[Optional] Click **Next** to add any additional data sources that you want to associate with your people of interest.</span></span>

7. <span data-ttu-id="927ac-119">Optional Selezionare **Aggiorna** per assegnare le posizioni di contenuto, come le cassette postali, i siti e i team a un utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-119">[Optional] Select **Update** to assign content locations, like mailboxes, sites, and Teams to a person.</span></span> 

8. <span data-ttu-id="927ac-120">Optional Nel riquadro a comparsa:</span><span class="sxs-lookup"><span data-stu-id="927ac-120">[Optional] In the flyout:</span></span>
   
    -  <span data-ttu-id="927ac-121">**Cassette postali di Exchange** -fare clic su **Scegli utenti, gruppi o team** e quindi fare di nuovo clic su **Scegli utenti, gruppi o team** .</span><span class="sxs-lookup"><span data-stu-id="927ac-121">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="927ac-122">Per aggiungere altre cassette postali, utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="927ac-122">To add more mailboxes, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="927ac-123">È inoltre possibile aggiungere cassette postali utilizzate per archiviare un gruppo di Microsoft 365 o un Microsoft Team Information.</span><span class="sxs-lookup"><span data-stu-id="927ac-123">You can also add mailboxes used to store an Microsoft 365 Group or a Microsoft Team information.</span></span> <span data-ttu-id="927ac-124">Selezionare la casella di controllo utente, gruppo, team, fare clic su **Scegli**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="927ac-124">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="927ac-125">Quando si fa clic su Scegli utenti, gruppi o team per specificare le cassette postali, lo strumento di selezione delle cassette postali visualizzato è vuoto.</span><span class="sxs-lookup"><span data-stu-id="927ac-125">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="927ac-126">Si tratta di un'impostazione predefinita per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="927ac-126">This is by design to enhance performance.</span></span> <span data-ttu-id="927ac-127">Per aggiungere persone a questo elenco, digitare un nome, almeno 3 caratteri, nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="927ac-127">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="927ac-128">**Siti di SharePoint** -fare clic su **Choose sites** , quindi fare clic su **Choose sites** again per specificare altri siti di SharePoint e OneDrive for business che è possibile aggiungere a una persona.</span><span class="sxs-lookup"><span data-stu-id="927ac-128">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you wwant to add to a person.</span></span> <span data-ttu-id="927ac-129">È inoltre possibile aggiungere l'URL per il sito di SharePoint per un gruppo di Microsoft 365 o un team di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="927ac-129">You can also add the URL for the SharePoint site for an Microsoft 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="927ac-130">Digitare l'URL per ogni sito che si desidera assegnare.</span><span class="sxs-lookup"><span data-stu-id="927ac-130">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="927ac-131">Fare clic su **Scegli**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="927ac-131">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="927ac-132">**Microsoft teams** -fare clic su **Scegli team** e quindi fare di nuovo clic su **Scegli squadre** per visualizzare un elenco di gruppi di team Microsoft che la persona è un membro di oggi.</span><span class="sxs-lookup"><span data-stu-id="927ac-132">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the person is a member of today.</span></span> <span data-ttu-id="927ac-133">Selezionare i team che si desidera aggiungere alla persona.</span><span class="sxs-lookup"><span data-stu-id="927ac-133">Select the Teams that you want to add to the person.</span></span> <span data-ttu-id="927ac-134">Una volta selezionata, il sistema identificherà automaticamente & selezionare il sito di SharePoint associato e la cassetta postale del gruppo associata a quel team Microsoft.</span><span class="sxs-lookup"><span data-stu-id="927ac-134">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="927ac-135">Fare clic su **Scegli**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="927ac-135">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="927ac-136">Per aggiungere ulteriori Microsoft teams, sarà necessario aggiungere separatamente la cassetta postale e il sito di SharePoint come illustrato in alto.</span><span class="sxs-lookup"><span data-stu-id="927ac-136">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="927ac-137">Dopo aver completato la mappatura delle origini dati alle persone di interesse, è possibile visualizzare il riepilogo di tutte le cassette postali, i siti e i team appena aggiunti.</span><span class="sxs-lookup"><span data-stu-id="927ac-137">After you have finished mapping data sources to people of interest, you can see the summary of total mailboxes, sites, and Teams that you just added.</span></span> <span data-ttu-id="927ac-138">Se si mappano altre origini dati a persone di interesse e l'ambito della ricerca da parte di persone di interesse, la mappatura del documento a persone di interesse persiste durante l'indagine, facilitando l'organizzazione di prove o la generazione di report da parte di persone di interesse.</span><span class="sxs-lookup"><span data-stu-id="927ac-138">If you map any additional data sources to people of interest and scope your search by people of interest, the mapping of document to people of interest persist throughout the investigation, making it easier to organize evidence or generate report by people of interest.</span></span> 

## <a name="view-additional-people-of-interest-information"></a><span data-ttu-id="927ac-139">Visualizzazione di altre persone di informazioni sugli interessi</span><span class="sxs-lookup"><span data-stu-id="927ac-139">View additional people of interest information</span></span>

<span data-ttu-id="927ac-140">Nella scheda **persone di interesse** , fare clic su una persona che si Adeed.</span><span class="sxs-lookup"><span data-stu-id="927ac-140">In **People of interest** tab, click on a person that you adeed.</span></span> <span data-ttu-id="927ac-141">In un riquadro a comparsa, vedrai:</span><span class="sxs-lookup"><span data-stu-id="927ac-141">In a flyout, you'll see:</span></span>

- <span data-ttu-id="927ac-142">Informazioni di contatto</span><span class="sxs-lookup"><span data-stu-id="927ac-142">Contact information</span></span>

  - <span data-ttu-id="927ac-143">**Nome**visualizzato: il nome del Peron visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="927ac-143">**Display Name**: The peron's name displayed in the address book.</span></span> <span data-ttu-id="927ac-144">Questo è in genere la combinazione del nome, dell'iniziale e del cognome.</span><span class="sxs-lookup"><span data-stu-id="927ac-144">This is usually the combination of first name, middle initial and last name.</span></span>
  - <span data-ttu-id="927ac-145">**Posta/SMTP**: indirizzo SMTP della persona, ad esempio Jeff@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="927ac-145">**Mail/SMTP**: The SMTP address of the person, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="927ac-146">**Titolo**: titolo del processo.</span><span class="sxs-lookup"><span data-stu-id="927ac-146">**Title**: Job title.</span></span>
  - <span data-ttu-id="927ac-147">**Reparto**: il nome del reparto in cui lavora la persona.</span><span class="sxs-lookup"><span data-stu-id="927ac-147">**Department**: The name of the department in which the person works.</span></span>
  - <span data-ttu-id="927ac-148">**Responsabile**: responsabile del personale.</span><span class="sxs-lookup"><span data-stu-id="927ac-148">**Manager**: The person's manager.</span></span> <span data-ttu-id="927ac-149">Manager riceve tutte le comunicazioni di escalation per questa persona.</span><span class="sxs-lookup"><span data-stu-id="927ac-149">Manager receives any escalation communications for this person.</span></span>
  
- <span data-ttu-id="927ac-150">Informazioni sulle posizioni</span><span class="sxs-lookup"><span data-stu-id="927ac-150">Location information</span></span>

  - <span data-ttu-id="927ac-151">**Città**: la città in cui si trova la persona.</span><span class="sxs-lookup"><span data-stu-id="927ac-151">**City**: The city in which the person is located.</span></span>
  - <span data-ttu-id="927ac-152">**Stato**: lo stato o la provincia in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-152">**State**: The state or province in which the person is located.</span></span>
  - <span data-ttu-id="927ac-153">**Paese/area geografica**: il paese/area geografica in cui si trova la persona; ad esempio, "US" o "UK".</span><span class="sxs-lookup"><span data-stu-id="927ac-153">**Country/Region**: The country/region in which the person is located; for example, "US" or "UK".</span></span>
  - <span data-ttu-id="927ac-154">**Office**: posizione dell'ufficio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-154">**Office**: The office location of the person.</span></span>

- <span data-ttu-id="927ac-155">Stato di elaborazione</span><span class="sxs-lookup"><span data-stu-id="927ac-155">Processing status</span></span>

  - <span data-ttu-id="927ac-156">**Stato di indicizzazione**: stato del Deep indicizzazione delle origini dati</span><span class="sxs-lookup"><span data-stu-id="927ac-156">**Indexing status**: Status of deep indexing the data sources</span></span>
  - <span data-ttu-id="927ac-157">**Indicizzazione dell'ultimo aggiornamento**: timestamp del momento in cui il processo di indicizzazione Deep è stato attivato.</span><span class="sxs-lookup"><span data-stu-id="927ac-157">**Indexing Last Updated Time**: Timestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="927ac-158">**Origini dati**: Visualizza il numero di cassette postali, siti e team mappati alla persona</span><span class="sxs-lookup"><span data-stu-id="927ac-158">**Data sources**: Shows the count of mailboxes, sites, and Teams mapped to the person</span></span>

- <span data-ttu-id="927ac-159">Indice di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="927ac-159">Update index</span></span>
    - <span data-ttu-id="927ac-160">È possibile reindicizzare le origini dati di questa persona.</span><span class="sxs-lookup"><span data-stu-id="927ac-160">You can re-index this person's data sources.</span></span> 

- <span data-ttu-id="927ac-161">Visualizzazione attività</span><span class="sxs-lookup"><span data-stu-id="927ac-161">View activity</span></span> 

    - <span data-ttu-id="927ac-162">È possibile visualizzare e cercare i registri delle attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-162">You can view and search user's activity logs.</span></span> <span data-ttu-id="927ac-163">Per ulteriori informazioni, vedere [View people of interest Activity](view-people-of-interest-activity.md)</span><span class="sxs-lookup"><span data-stu-id="927ac-163">For more information, see [View people of interest activity](view-people-of-interest-activity.md)</span></span> 
