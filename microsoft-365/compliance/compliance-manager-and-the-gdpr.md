---
title: Microsoft Compliance Manager e GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager è uno strumento gratuito di valutazione dei rischi basato sul flusso di lavoro in Microsoft Service Trust Portal. Compliance Manager consente di tenere traccia, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595803"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="afdd5-104">Microsoft Compliance Manager e GDPR</span><span class="sxs-lookup"><span data-stu-id="afdd5-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="afdd5-105">Il Regolamento generale sulla protezione dei dati (GDPR) evaso dall'Unione Europea può influire sulla strategia di conformità e impone azioni specifiche per gestire le informazioni su utenti e clienti utilizzate in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="afdd5-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="afdd5-106">Impostazioni di privacy dell'utente</span><span class="sxs-lookup"><span data-stu-id="afdd5-106">User Privacy settings</span></span>

<span data-ttu-id="afdd5-107">Alcune normative richiedono che un'organizzazione sia in grado di eliminare i dati della cronologia utente.</span><span class="sxs-lookup"><span data-stu-id="afdd5-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="afdd5-108">Compliance Manager fornisce **funzioni per le impostazioni di privacy** degli utenti che consentono agli amministratori di:</span><span class="sxs-lookup"><span data-stu-id="afdd5-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="afdd5-109">Cercare un utente</span><span class="sxs-lookup"><span data-stu-id="afdd5-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="afdd5-110">Esportare un report di cronologia dei dati dell'account</span><span class="sxs-lookup"><span data-stu-id="afdd5-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="afdd5-111">Eliminare la cronologia dei dati dell'utente</span><span class="sxs-lookup"><span data-stu-id="afdd5-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="afdd5-112">Cercare un utente</span><span class="sxs-lookup"><span data-stu-id="afdd5-112">Search for a user</span></span>

<span data-ttu-id="afdd5-113">Cercare un account utente:</span><span class="sxs-lookup"><span data-stu-id="afdd5-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="afdd5-114">Immettere l'alias di posta elettronica dell'utente (le informazioni a sinistra del simbolo @) e scegliere il nome di dominio dall'elenco dei suffissi di dominio a destra.</span><span class="sxs-lookup"><span data-stu-id="afdd5-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="afdd5-115">Per le organizzazioni con più domini registrati, controllare il suffisso del nome di dominio per verificare che sia corretto.</span><span class="sxs-lookup"><span data-stu-id="afdd5-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="afdd5-116">Dopo aver immesso correttamente il nome utente, selezionare **Cerca.**</span><span class="sxs-lookup"><span data-stu-id="afdd5-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="afdd5-117">Per gli account utente non restituiti, nella pagina viene visualizzato **Utente non trovato.**</span><span class="sxs-lookup"><span data-stu-id="afdd5-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="afdd5-118">Controllare le informazioni sull'indirizzo di posta elettronica dell'utente e apportare le correzioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="afdd5-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="afdd5-119">Per riprovare, selezionare **Cerca.**</span><span class="sxs-lookup"><span data-stu-id="afdd5-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="afdd5-120">Per gli account utente restituiti, il testo del pulsante cambia da **Ricerca** a **Cancella.**</span><span class="sxs-lookup"><span data-stu-id="afdd5-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="afdd5-121">Ciò indica che l'account utente restituito è il contesto operativo per le funzioni aggiuntive e che queste funzioni si applicano a questo account utente.</span><span class="sxs-lookup"><span data-stu-id="afdd5-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="afdd5-122">Per cancellare i risultati della ricerca e cercare un altro utente, selezionare **Cancella.**</span><span class="sxs-lookup"><span data-stu-id="afdd5-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="afdd5-123">Esportare un report di cronologia dei dati dell'account</span><span class="sxs-lookup"><span data-stu-id="afdd5-123">Export a report of account data history</span></span>

<span data-ttu-id="afdd5-124">Per ogni account utente identificato, puoi generare un report delle dipendenze collegate all'account.</span><span class="sxs-lookup"><span data-stu-id="afdd5-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="afdd5-125">Queste informazioni consentono di riassegnare le attività aperte o di garantire l'accesso alle prove caricate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="afdd5-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="afdd5-126">Per generare ed esportare un report:</span><span class="sxs-lookup"><span data-stu-id="afdd5-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="afdd5-127">Selezionare **Esporta** per generare e scaricare un report delle attività di controllo di Compliance Manager attualmente assegnate all'account utente restituito e l'elenco dei documenti caricati da tale utente.</span><span class="sxs-lookup"><span data-stu-id="afdd5-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="afdd5-128">Se non sono presenti azioni assegnate o documenti caricati, viene visualizzato il messaggio di errore "Nessun dato per questo utente".</span><span class="sxs-lookup"><span data-stu-id="afdd5-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="afdd5-129">Il report viene scaricato in background nella finestra del browser attiva, se non viene visualizzata una finestra popup di download che si desidera controllare la cronologia di download del browser.</span><span class="sxs-lookup"><span data-stu-id="afdd5-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="afdd5-130">Aprire il documento per visualizzare i dati del report.</span><span class="sxs-lookup"><span data-stu-id="afdd5-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afdd5-131">I dati del report non sono un elenco cronologico che mantiene e visualizza le modifiche di stato alla cronologia delle assegnazioni delle attività.</span><span class="sxs-lookup"><span data-stu-id="afdd5-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="afdd5-132">Il report generato è uno snapshot delle attività di controllo assegnate al momento dell'esecuzione del report (data e timestamp scritti nel report).</span><span class="sxs-lookup"><span data-stu-id="afdd5-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="afdd5-133">Ad esempio, qualsiasi successiva riassegnazione delle attività comporta dati di report snapshot diversi se il report viene generato di nuovo per lo stesso utente.</span><span class="sxs-lookup"><span data-stu-id="afdd5-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="afdd5-134">Eliminare la cronologia dei dati dell'utente</span><span class="sxs-lookup"><span data-stu-id="afdd5-134">Delete user data history</span></span>

<span data-ttu-id="afdd5-135">Imposta tutte le attività di controllo assegnate all'utente restituito su "non assegnato".</span><span class="sxs-lookup"><span data-stu-id="afdd5-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="afdd5-136">Imposta il **valore caricato per** i documenti caricati dall'utente restituito su "utente rimosso".</span><span class="sxs-lookup"><span data-stu-id="afdd5-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="afdd5-137">Per eliminare l'elemento azione dell'account utente e la cronologia di caricamento dei documenti:</span><span class="sxs-lookup"><span data-stu-id="afdd5-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="afdd5-138">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="afdd5-138">Select **Delete**.</span></span>

    <span data-ttu-id="afdd5-139">Viene visualizzata una finestra di dialogo di conferma: " In questo modo vengono rimosse tutte le assegnazioni dell'elemento azione di controllo e la cronologia di caricamento del documento *per l'utente selezionato. Questa azione è permanente. Si è sicuri di voler continuare?*"</span><span class="sxs-lookup"><span data-stu-id="afdd5-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="afdd5-140">Per continuare selezionare **OK,** altrimenti scegliere **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="afdd5-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
