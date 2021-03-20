---
title: Lavorare con Microsoft Consulting Services
description: preparazione e passaggi da seguire per lavorare con MCS per creare un pacchetto delle app
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, MCS, creazione di pacchetti
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 04b0c7905c83be2afa46abcfb2d4bb5cd9735e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909227"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="55886-104">Lavorare con Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="55886-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="55886-105">Puoi interagire con Microsoft Consulting Services (MCS) per ottenere le tue app in pacchetto per l'uso con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="55886-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="55886-106">Per dettagli esatti, contatta il rappresentante dell'account per contattare MCS e impostare l'ambito del progetto di creazione di pacchetti di app specifico.</span><span class="sxs-lookup"><span data-stu-id="55886-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="55886-107">Ruoli e responsabilità</span><span class="sxs-lookup"><span data-stu-id="55886-107">Roles and responsibilities</span></span>

<span data-ttu-id="55886-108">Per usare il pacchetto dell'app MCS, **devi fornire questi elementi:**</span><span class="sxs-lookup"><span data-stu-id="55886-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="55886-109">I file del programma di installazione di origine(ad esempio, setup.exe o msi).</span><span class="sxs-lookup"><span data-stu-id="55886-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="55886-110">Le istruzioni di installazione, che specificano i dettagli sull'aspetto dell'installazione finale.</span><span class="sxs-lookup"><span data-stu-id="55886-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="55886-111">Ad esempio, dovrebbe essere presente un collegamento desktop all'app?</span><span class="sxs-lookup"><span data-stu-id="55886-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="55886-112">Qual è la visibilità dell'app?</span><span class="sxs-lookup"><span data-stu-id="55886-112">What should the app's visibility be?</span></span> <span data-ttu-id="55886-113">L'app deve connettersi a un server e, in tal caso, quale?</span><span class="sxs-lookup"><span data-stu-id="55886-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="55886-114">Per informazioni dettagliate, vedere il modello di richiesta [di creazione di pacchetti dell'applicazione](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="55886-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="55886-115">Devi eseguire test di accettazione personalizzati per verificare che l'app funzioni come necessario nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="55886-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="55886-116">**MCS si occuperà di queste azioni:**</span><span class="sxs-lookup"><span data-stu-id="55886-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="55886-117">Verifica se l'app è proibita o limitata nell'ambiente Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="55886-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="55886-118">Test di installazione, avvio e disinstallazione dell'app per garantire la compatibilità con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="55886-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="55886-119">Se MCS rileva un problema di compatibilità, l'app verrà consegnata al programma [Desktop App Assure](/fasttrack/win-10-desktop-app-assure) per la correzione.</span><span class="sxs-lookup"><span data-stu-id="55886-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="55886-120">Creare il pacchetto dell'app per le specifiche e quindi testare la distribuzione dell'app tramite Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="55886-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="55886-121">Pianificazione recapito app</span><span class="sxs-lookup"><span data-stu-id="55886-121">App delivery schedule</span></span>

<span data-ttu-id="55886-122">Avvia il processo di creazione di pacchetti caricando le informazioni sull'app nel portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="55886-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="55886-123">Il team di creazione di pacchetti rivede i nuovi invii ogni giovedì.</span><span class="sxs-lookup"><span data-stu-id="55886-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="55886-124">Dopo la revisione e la creazione del pacchetto, le app in pacchetto vengono recapitate il venerdì seguente.</span><span class="sxs-lookup"><span data-stu-id="55886-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="55886-125">L'avvio può contenere fino a cinque app a settimana, ma il servizio può essere ridimensionato in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="55886-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendario che mostra il flusso di app di giovedì (il 21 in questo esempio), convalida multimediale il giorno successivo, creazione di pacchetti il lunedì successivo (il 25) e recapito dell'app il venerdì successivo (il 29)](../../media/MCS-cal.png)

<span data-ttu-id="55886-127">Una volta recapitata l'app, ti verrà notificato.</span><span class="sxs-lookup"><span data-stu-id="55886-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="55886-128">A questo punto, hai 21 giorni per eseguire il test di accettazione e approvare il lavoro nel portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="55886-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="55886-129">Se rileva un problema con l'app durante il test di accettazione, rifiuta l'app nel portale Microsoft Managed Desktop e verrà connesso tramite posta elettronica con un packager MCS per comprendere e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="55886-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="55886-130">Test di account e ambiente</span><span class="sxs-lookup"><span data-stu-id="55886-130">Testing accounts and environment</span></span>

<span data-ttu-id="55886-131">Per consentire al team di creazione di pacchetti di completare la migrazione a Microsoft Intune, è consigliabile fornire determinate autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="55886-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="55886-132">Accesso alle funzionalità di distribuzione delle app di Microsoft Intune per il programma di creazione di pacchetti per aggiungere e assegnare l'app</span><span class="sxs-lookup"><span data-stu-id="55886-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="55886-133">Gruppi di test, account utente e licenze per i packager per poter testare le app</span><span class="sxs-lookup"><span data-stu-id="55886-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="55886-134">McS utilizzerà tali autorizzazioni per eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55886-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="55886-135">Verifica del funzionamento dell'app nella macchina virtuale configurata per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="55886-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="55886-136">Caricamento dell'app in Microsoft Intune per la distribuzione agli utenti</span><span class="sxs-lookup"><span data-stu-id="55886-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="55886-137">Senza queste autorizzazioni, è possibile che MCS si sposti in avanti, ma non sarà in grado di caricare le applicazioni nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="55886-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>