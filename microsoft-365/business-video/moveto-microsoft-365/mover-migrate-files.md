---
title: 'Eseguire la migrazione dei file di Google Microsoft 365 per le aziende '
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
description: Scopri come eseguire la migrazione dei file di Google Microsoft 365 per le aziende usando Mover.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913575"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="eeac1-103">Eseguire la migrazione dei file di Google Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="eeac1-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="eeac1-104">Quando si passa a Microsoft 365 per le aziende, è necessario eseguire la migrazione dei file da Google Drive.</span><span class="sxs-lookup"><span data-stu-id="eeac1-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="eeac1-105">Puoi usare l'app Mover per spostare i file dalle unità personali e condivise.</span><span class="sxs-lookup"><span data-stu-id="eeac1-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="eeac1-106">Per ulteriori informazioni, vedere [Mover Cloud Migration.](/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="eeac1-106">For more information, see [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="eeac1-107">Mover crea una copia dei file e sposta le copie in Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="eeac1-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="eeac1-108">Anche i file originali rimarranno in Google Drives.</span><span class="sxs-lookup"><span data-stu-id="eeac1-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="eeac1-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="eeac1-109">Before you start</span></span>

<span data-ttu-id="eeac1-110">Tutti gli utenti devono aver eseguito l'accesso a Microsoft 365 per le aziende e aver configurato le proprie OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="eeac1-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="eeac1-111">A tale scopo, passare [a office.com](https://office.com), accedere con le credenziali Microsoft 365 per le aziende e quindi scegliere OneDrive.</span><span class="sxs-lookup"><span data-stu-id="eeac1-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="eeac1-112">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="eeac1-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="eeac1-113">Installare Mover</span><span class="sxs-lookup"><span data-stu-id="eeac1-113">Install Mover</span></span>

1. <span data-ttu-id="eeac1-114">Accedi alla console di amministrazione di Google Workspace [all'indirizzo admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="eeac1-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="eeac1-115">Choose **Apps**  >  **Google Workspace Marketplace apps** Add app to Domain Install  >  **list**.</span><span class="sxs-lookup"><span data-stu-id="eeac1-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="eeac1-116">Cerca Mover e selezionalo.</span><span class="sxs-lookup"><span data-stu-id="eeac1-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="eeac1-117">Scegliere **Domain Install**, quindi **Continue**.</span><span class="sxs-lookup"><span data-stu-id="eeac1-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="eeac1-118">Rivedere le autorizzazioni, selezionare la casella di controllo per accettare i termini, quindi selezionare **Consenti,** scegliere **Avanti,** quindi **Fatto.**</span><span class="sxs-lookup"><span data-stu-id="eeac1-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="eeac1-119">Creare connettori ed eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="eeac1-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="eeac1-120">Torna alle **app di Google Workspace Marketplace.**</span><span class="sxs-lookup"><span data-stu-id="eeac1-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="eeac1-121">Aggiorna il browser e seleziona l'app **Mover.**</span><span class="sxs-lookup"><span data-stu-id="eeac1-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="eeac1-122">Scorrere verso il basso e scegliere il collegamento di spostamento universale.</span><span class="sxs-lookup"><span data-stu-id="eeac1-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="eeac1-123">Seleziona **Autorizza nuovo connettore,** individua **G Suite (amministratore)** e scegli **Autorizza**.</span><span class="sxs-lookup"><span data-stu-id="eeac1-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="eeac1-124">Modificare il **nome visualizzato**, se si desidera, quindi selezionare **Autorizza**.</span><span class="sxs-lookup"><span data-stu-id="eeac1-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="eeac1-125">Scegli un account amministratore di Google, rivedi le autorizzazioni, quindi seleziona **Consenti.**</span><span class="sxs-lookup"><span data-stu-id="eeac1-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="eeac1-126">Mover visualizza il numero di unità del team e unità utente individuate.</span><span class="sxs-lookup"><span data-stu-id="eeac1-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="eeac1-127">In **Seleziona destinazione** scegliere **Autorizza nuovo connettore,** individuare **Office 365** e selezionare **Autorizza**.</span><span class="sxs-lookup"><span data-stu-id="eeac1-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="eeac1-128">Per concedere le autorizzazioni per l'app Mover nel Azure Active Directory, passa a [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="eeac1-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="eeac1-129">Seleziona **Office 365 Mover**, **Autorizzazioni**, Concedi il **consenso dell'amministratore per la tua azienda**.</span><span class="sxs-lookup"><span data-stu-id="eeac1-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="eeac1-130">Scegliere l'account, esaminare le autorizzazioni e selezionare **Accetta.**</span><span class="sxs-lookup"><span data-stu-id="eeac1-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="eeac1-131">Scegliere **Proprietà** e verificare che **l'assegnazione utente necessaria?** sia attivata.</span><span class="sxs-lookup"><span data-stu-id="eeac1-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="eeac1-132">Tornare all'app Mover, modificare il **nome** visualizzato, se si desidera, scegliere **Autorizza** e quindi selezionare un account di amministratore Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eeac1-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="eeac1-133">Mover ti informerà sul numero di siti SharePoint Online (o SPO) e utenti individuati.</span><span class="sxs-lookup"><span data-stu-id="eeac1-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="eeac1-134">Scegliere **Continua l'installazione della** migrazione, selezionare Aggiungi **utenti,** quindi Individua e aggiungi utenti **automaticamente.**</span><span class="sxs-lookup"><span data-stu-id="eeac1-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="eeac1-135">L'app Mover tenterà di mappare le unità dal percorso di origine in Google al percorso di destinazione in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eeac1-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="eeac1-136">Se un'unità non viene mappata automaticamente, aggiungerne il percorso di destinazione a un file CSV, che verrà utilizzato in un secondo momento per eseguire la migrazione dell'unità condivisa in una raccolta documenti SharePoint condivisa.</span><span class="sxs-lookup"><span data-stu-id="eeac1-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="eeac1-137">In questo caso, è stato aggiunto un sito SharePoint denominato File migrati e preso nota dell'URL per la pagina dei documenti.</span><span class="sxs-lookup"><span data-stu-id="eeac1-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="eeac1-138">Abbiamo quindi creato un file CSV usando il formato Percorso di origine, Percorso di destinazione e Tag.</span><span class="sxs-lookup"><span data-stu-id="eeac1-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="eeac1-139">Per informazioni [dettagliate, vedere aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="eeac1-139">For details see [aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="eeac1-140">Quando si aggiunge l'URL percorso di destinazione, rimuovere tutti gli elementi dopo Documenti condivisi.</span><span class="sxs-lookup"><span data-stu-id="eeac1-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="eeac1-141">Ad esempio, questo URL completo non funziona: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="eeac1-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="eeac1-142">Passare a: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="eeac1-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="eeac1-143">Una volta pronto il file CSV, selezionare **Azioni di migrazione**, **Aggiungi** alla migrazione , Scegliere un file **da caricare**.</span><span class="sxs-lookup"><span data-stu-id="eeac1-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="eeac1-144">Passare al file CSV, selezionarlo, quindi scegliere **Apri.**</span><span class="sxs-lookup"><span data-stu-id="eeac1-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="eeac1-145">Selezionare le unità utente di cui si desidera eseguire la migrazione dei file, quindi scegliere **Avvia migrazione utenti**.</span><span class="sxs-lookup"><span data-stu-id="eeac1-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="eeac1-146">Esaminare le informazioni sulla migrazione, scegliere quando avviare la migrazione, accettare i Termini e **condizioni,** quindi selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="eeac1-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="eeac1-147">L'app Mover ti informerà al termine del processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="eeac1-147">The Mover app will inform you when the migration process is complete.</span></span>