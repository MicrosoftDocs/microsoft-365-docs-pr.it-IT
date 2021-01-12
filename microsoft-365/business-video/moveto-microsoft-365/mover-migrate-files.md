---
title: 'Eseguire la migrazione di file di Google a Microsoft 365 for business '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come eseguire la migrazione di file di Google a Microsoft 365 for business tramite Mover.
ms.openlocfilehash: a6f9dbf7803cb552c23b6c6abb13d13d6f3eda5d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794638"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="6f4a0-103">Eseguire la migrazione di file di Google a Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="6f4a0-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="6f4a0-104">Quando ci si sposta su Microsoft 365 for business, è necessario eseguire la migrazione dei file da Google Drive.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="6f4a0-105">È possibile utilizzare l'app Mover per spostare i file da unità personali e condivise.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="6f4a0-106">Per ulteriori informazioni, vedere [Mover cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="6f4a0-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="6f4a0-107">Mover renderà una copia dei file e sposterà le copie in Microsoft 365 for business.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="6f4a0-108">Anche i file originali rimarranno nelle unità di Google.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="6f4a0-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6f4a0-109">Before you start</span></span>

<span data-ttu-id="6f4a0-110">Tutti gli utenti devono avere effettuato l'accesso a Microsoft 365 for business e impostare la propria OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="6f4a0-111">A tale scopo, accedere a [Office.com](https://office.com), accedere con le credenziali di Microsoft 365 per le aziende e quindi scegliere OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="6f4a0-112">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="6f4a0-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="6f4a0-113">Installazione di Mover</span><span class="sxs-lookup"><span data-stu-id="6f4a0-113">Install Mover</span></span>

1. <span data-ttu-id="6f4a0-114">Accedere alla console di amministrazione di Google Workspace all' [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="6f4a0-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="6f4a0-115">Scegliere **app**, **Google Workspace Marketplace Apps** e quindi **aggiungere app all'elenco di installazione di dominio**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="6f4a0-116">Cercare Mover e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="6f4a0-117">Scegliere **Domain install**, quindi **continue**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="6f4a0-118">Controllare le autorizzazioni, selezionare la casella di controllo per accettare i termini, quindi selezionare **Consenti**, quindi **fare** clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="6f4a0-119">Creare connettori ed eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="6f4a0-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="6f4a0-120">Tornare alle **App Marketplace di Google Workspace**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="6f4a0-121">Aggiornare il browser e selezionare l'app **Mover** .</span><span class="sxs-lookup"><span data-stu-id="6f4a0-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="6f4a0-122">Scorrere verso il basso e scegliere il collegamento di spostamento universale.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="6f4a0-123">Selezionare **autorizza nuovo connettore**, individuare **G Suite (amministratore)** e scegliere **autorizza**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="6f4a0-124">Se lo si desidera, modificare il **nome visualizzato**, quindi selezionare **autorizza**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="6f4a0-125">Scegliere un account di amministratore di Google, esaminare le autorizzazioni e quindi fare clic su **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="6f4a0-126">Mover Visualizza il numero di unità di team e unità utente individuate.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="6f4a0-127">In **Seleziona destinazione**, scegliere **autorizza nuovo connettore**, individuare **Office 365** e selezionare **autorizza**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="6f4a0-128">Per concedere le autorizzazioni per l'app Mover in Azure Active Directory, passare a [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="6f4a0-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="6f4a0-129">Selezionare **Office 365 Mover**, **Permissions**, **concedere il consenso dell'amministratore per la società**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="6f4a0-130">Scegliere l'account, esaminare le autorizzazioni e selezionare **accetta**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="6f4a0-131">Scegliere **Proprietà** e verificare che l' **assegnazione degli utenti sia obbligatoria?** è attivata.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="6f4a0-132">Tornare all'app Mover, cambiare il **nome visualizzato**, se lo si desidera, scegliere **autorizza**, quindi selezionare un account di amministratore Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="6f4a0-133">Mover vi informerà sul numero di siti e utenti di SharePoint Online (o SPO) individuati.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="6f4a0-134">Scegliere **continue Migration Setup**, selezionare **Aggiungi utenti**, quindi **individuare e aggiungere automaticamente gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="6f4a0-135">L'app Mover tenterà di mappare le unità dal percorso di origine di Google al percorso di destinazione in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="6f4a0-136">Se un'unità non esegue il mapping automatico, aggiungere il percorso di destinazione a un file CSV, che verrà utilizzato in un secondo momento per eseguire la migrazione dell'unità condivisa in una raccolta documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="6f4a0-137">In questo caso, è stato aggiunto un sito di SharePoint denominato file migrati e viene annotato l'URL della pagina documenti.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="6f4a0-138">È stato quindi creato un file CSV utilizzando il formato del percorso di origine, il percorso di destinazione e i tag.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="6f4a0-139">Per informazioni dettagliate, vedere [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="6f4a0-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="6f4a0-140">Quando si aggiunge l'URL del percorso di destinazione, rimuovere tutto dopo la condivisione di documenti, ad esempio, l'URL completo non funzionerà: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="6f4a0-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="6f4a0-141">Passare a: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="6f4a0-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="6f4a0-142">Una volta che il file CSV è pronto, seleziona **azioni di migrazione**, **Aggiungi alla migrazione**, **Scegli un file da caricare**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="6f4a0-143">Passare al file CSV, selezionarlo e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="6f4a0-144">Selezionare le unità utente di cui si desidera eseguire la migrazione e quindi fare clic su **Avvia migrazione utenti**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="6f4a0-145">Leggere le informazioni sulla migrazione, scegliere quando avviare la migrazione, accettare i **termini e le condizioni**, quindi selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="6f4a0-146">L'app Mover informerà quando il processo di migrazione è stato completato.</span><span class="sxs-lookup"><span data-stu-id="6f4a0-146">The Mover app will inform you when the migration process is complete.</span></span>