---
title: Utilizzo di Microsoft Consulting Services
description: preparazione e passaggi da seguire per lavorare con MCS per il pacchetto delle app
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, Apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3687966fd49db3fd58c4ecbb3917e45ec6dfa3c3
ms.sourcegitcommit: b9663acecf0bfdca2486818ec7e08a6f882d0dc9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "35425739"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="059dc-104">Utilizzo di Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="059dc-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="059dc-105">È possibile collaborare con Microsoft Consulting Services (MCS) per ottenere le app in pacchetti per l'utilizzo con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="059dc-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="059dc-106">Per i dettagli esatti, collaborare con il proprio account Representative per contattare MCS e l'ambito del progetto di packaging app specifico.</span><span class="sxs-lookup"><span data-stu-id="059dc-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="059dc-107">Ruoli e responsabilità</span><span class="sxs-lookup"><span data-stu-id="059dc-107">Roles and responsibilities</span></span>

<span data-ttu-id="059dc-108">Per utilizzare la confezione dell'app MCS, **è necessario fornire questi elementi**:</span><span class="sxs-lookup"><span data-stu-id="059dc-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="059dc-109">File del programma di installazione di origine (ad esempio, Setup. exe o. msi).</span><span class="sxs-lookup"><span data-stu-id="059dc-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="059dc-110">Istruzioni di installazione, specificando i dettagli sul modo in cui deve essere consentita l'installazione finale.</span><span class="sxs-lookup"><span data-stu-id="059dc-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="059dc-111">Ad esempio, se è presente un collegamento sul desktop per l'app?</span><span class="sxs-lookup"><span data-stu-id="059dc-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="059dc-112">Che cosa dovrebbe essere la visibilità dell'app?</span><span class="sxs-lookup"><span data-stu-id="059dc-112">What should the app's visibility be?</span></span> <span data-ttu-id="059dc-113">Se l'app si connette a un server e, in caso affermativo, quale?</span><span class="sxs-lookup"><span data-stu-id="059dc-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="059dc-114">Per informazioni dettagliate, vedere il [modello di richiesta di pacchettizzazione dell'applicazione](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="059dc-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="059dc-115">È necessario eseguire un test di accettazione personalizzato per verificare che l'app funzioni come necessario nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="059dc-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="059dc-116">**MCS si occuperà di queste azioni:**</span><span class="sxs-lookup"><span data-stu-id="059dc-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="059dc-117">Controllare se l'app è vietata o limitata nell'ambiente Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="059dc-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="059dc-118">Verifica dell'installazione, dell'avvio e della disinstallazione dell'app per garantire la compatibilità con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="059dc-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="059dc-119">Se MCS individua un problema di compatibilità, disinvierà l'app al programma [app desktop assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) per la correzione.</span><span class="sxs-lookup"><span data-stu-id="059dc-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="059dc-120">L'applicazione viene configurata per la specifica e quindi viene testata la distribuzione delle app tramite Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="059dc-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="059dc-121">Pianificazione del recapito delle app</span><span class="sxs-lookup"><span data-stu-id="059dc-121">App delivery schedule</span></span>

<span data-ttu-id="059dc-122">Avviare il processo di creazione del pacchetto caricando le informazioni sull'app nel portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="059dc-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="059dc-123">Il team di packaging esamina i nuovi invii ogni Giovedi.</span><span class="sxs-lookup"><span data-stu-id="059dc-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="059dc-124">Dopo la revisione e la confezione, le app in pacchetti vengono recapitate il venerdì seguente.</span><span class="sxs-lookup"><span data-stu-id="059dc-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="059dc-125">È possibile creare pacchetti fino a cinque app alla settimana, ma il servizio può essere ridimensionato per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="059dc-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendario che mostra la revisione, il packaging e le date di consegna delle app](images/MCS-cal.png)

<span data-ttu-id="059dc-127">Una volta che l'app è stata recapitata, verrà inviata una notifica.</span><span class="sxs-lookup"><span data-stu-id="059dc-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="059dc-128">A questo punto, sono necessari 21 giorni per eseguire il test di accettazione e disconnettersi sul lavoro nel portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="059dc-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="059dc-129">Se si scopre qualche problema con l'app durante il test di accettazione, rifiutare l'applicazione nel portale Microsoft Managed Desktop e si sarà connessi tramite posta elettronica con un Packager MCS per comprendere e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="059dc-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="059dc-130">Verifica degli account e dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="059dc-130">Testing accounts and environment</span></span>

<span data-ttu-id="059dc-131">Affinché il team di packaging completi la migrazione a Microsoft Intune, è consigliabile fornire determinate autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="059dc-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="059dc-132">Accesso alle funzionalità di distribuzione delle app di Microsoft Intune per il Packager per aggiungere e assegnare l'app</span><span class="sxs-lookup"><span data-stu-id="059dc-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="059dc-133">Gruppi di test, account utente e licenze per i Packager per poter testare le app</span><span class="sxs-lookup"><span data-stu-id="059dc-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="059dc-134">MCS utilizzerà le autorizzazioni necessarie per eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="059dc-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="059dc-135">Garantire che l'app funzioni su una macchina virtuale configurata per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="059dc-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="059dc-136">Caricamento dell'app in Microsoft Intune per la distribuzione agli utenti</span><span class="sxs-lookup"><span data-stu-id="059dc-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="059dc-137">Se non si dispone di queste autorizzazioni, è possibile che MCS venga spostato in avanti, ma non sarà in grado di caricare le applicazioni nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="059dc-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


