---
title: Guida all'aggiornamento da Windows 7 a Windows 10
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Aggiornamento da Windows 7 a Windows 10.
ms.openlocfilehash: aaa1ce39e63aebeb3c2ab6678b3c1ade6791ab22
ms.sourcegitcommit: 7e806db3d44ec223754efe1e9613b2c7117c4788
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "34821040"
---
# <a name="windows-7-to-windows-10-manual-upgrade-step-by-step-guide"></a><span data-ttu-id="17275-103">Guida introduttiva per l’aggiornamento da Windows 7 a Windows 10</span><span class="sxs-lookup"><span data-stu-id="17275-103">Windows 7 to Windows 10 manual upgrade step-by-step guide</span></span>

<span data-ttu-id="17275-104">Questo articolo descrive il processo di aggiornamento manuale di un PC Windows 7 Enterprise a Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="17275-104">This article describes the process to manually upgrade a Windows 7 Enterprise PC to Windows 10 Enterprise.</span></span> <span data-ttu-id="17275-105">Per le altre versioni di Windows 7, come Home e Professional, il processo è molto simile, ma è anche possibile eseguire l'aggiornamento direttamente tramite lo strumento per la creazione di contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="17275-105">For other Windows 7 editions, such as Home and Professional, the process is very similar, but you also have the option to upgrade directly using the media creation tool.</span></span> <span data-ttu-id="17275-106">Gli aggiornamenti per tutte le versioni di Windows 7 a Windows 10 richiederanno un codice Product Key valido, una versione corrispondente o superiore di Windows, ad esempio, Windows 7 Professional può eseguire l'aggiornamento a Windows 10 Pro, ma non può essere aggiornato a Windows 10 Home.</span><span class="sxs-lookup"><span data-stu-id="17275-106">Upgrades for any edition of Windows 7 to Windows 10 will require a valid product key and matching or higher edition of Windows, for example Windows 7 Professional can upgrade to Windows 10 Pro, but cannot be upgraded to Windows 10 Home.</span></span> <span data-ttu-id="17275-107">In Windows 7 Ultimate richiede l’aggiornamento a Windows 10 Pro.</span><span class="sxs-lookup"><span data-stu-id="17275-107">Windows 7 Ultimate will need to be upgraded to Windows 10 Pro.</span></span>

## <a name="windows-10-upgrades-using-the-media-creation-tool-or-iso-files"></a><span data-ttu-id="17275-108">Aggiornamenti di Windows 10 con strumenti per la creazione di contenuti multimediali o file ISO</span><span class="sxs-lookup"><span data-stu-id="17275-108">Windows 10 upgrades using the media creation tool or ISO files</span></span>

<span data-ttu-id="17275-109">È possibile eseguire l'aggiornamento a Windows 10 direttamente utilizzando [lo strumento per la creazione di contenuti multimediali ](https://www.microsoft.com/en-us/software-download/windows10ISO) oppure usarlo per scaricare Windows 10 come file ISO.</span><span class="sxs-lookup"><span data-stu-id="17275-109">You can upgrade to Windows 10 directly using the [media creation tool](https://www.microsoft.com/en-us/software-download/windows10ISO) or use the it to download Windows 10 as an ISO file.</span></span> <span data-ttu-id="17275-110">È necessario constatare se il sistema corrente sia a 32 o 64 bit, la lingua predefinita e la versione di Windows 7 del sistema, ad esempio Home, Professional o Enterprise.</span><span class="sxs-lookup"><span data-stu-id="17275-110">You’ll need to note whether your current system is 32 or 64-bit, your system’s default language and edition of Windows 7 (e.g. Home, Professional, or Enterprise).</span></span> <span data-ttu-id="17275-111">In Windows 7 queste informazioni si trovano nel sistema del pannello di controllo \> Sistema e sicurezza \>.</span><span class="sxs-lookup"><span data-stu-id="17275-111">In Windows 7, this information is located in the Control Panel \> System and Security \> System.</span></span> <span data-ttu-id="17275-112">Lo strumento per la creazione di contenuti multimediali non supporta Windows 10 Enterprise per gli aggiornamenti, la creazione di supporti di installazione o il download di file ISO.</span><span class="sxs-lookup"><span data-stu-id="17275-112">The media creation tool does not support Windows 10 Enterprise for upgrades, creating installation media or downloading ISO files.</span></span> <span data-ttu-id="17275-113">Se si esegue l'aggiornamento da Windows 7 Enterprise, è necessario Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="17275-113">Windows 10 Enterprise is required if you are upgrading from Windows 7 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-1.png)

> <span data-ttu-id="17275-114">Opzioni strumenti per la creazione di Windows 10</span><span class="sxs-lookup"><span data-stu-id="17275-114">Windows 10 media creation tool options</span></span>

<span data-ttu-id="17275-115">Durante l' aggiornamento da Windows 7 Enterprise a Windows 10 Enterprise, è necessario scaricare il file ISO per la lingua e l'architettura (32 bit o 64 bit) dal [Centro servizi per contratti multilicenza.](https://www.microsoft.com/licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="17275-115">When upgrading from Windows 7 Enterprise to Windows 10 Enterprise, you’ll need to download the ISO file for your language and architecture (32-bit or 64-bit) from the [Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

<span data-ttu-id="17275-116">Se si prevede di eseguire l'aggiornamento con un file ISO, è necessario estrarre i file all'interno della ISO nel file system locale, in un'unità rimovibile o masterizzare il file ISO in un DVD.</span><span class="sxs-lookup"><span data-stu-id="17275-116">If you plan to perform the upgrade using an ISO file, you will need to extract the files within the ISO to either your local file system, to a removable drive, or you can burn the ISO file to a DVD.</span></span> <span data-ttu-id="17275-117">È possibile estrarre i file di installazione di nell'ISO con un PC con Windows 8 o versione successiva e salvare i file in uno spazio di archiviazione USB rimovibile o utilizzare un'applicazione come [7zip](https://www.7-zip.org/) per estrarre il contenuto del file ISO in una cartella nell'unità locale in Windows 7.</span><span class="sxs-lookup"><span data-stu-id="17275-117">You can extract the installation files within the ISO using a Windows 8 or newer PC and save these files to removable USB storage or use an application such as [7zip](https://www.7-zip.org/) to extract the contents of your ISO file to a folder on your local drive within Windows 7.</span></span>

<span data-ttu-id="17275-118">Dopo avere installato il supporto di installazione in Windows 7, è possibile avviare l'aggiornamento eseguendo setup.exe come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="17275-118">Once you have the install media available in Windows 7, you can initiate the upgrade by running setup.exe as shown below.</span></span>

<span data-ttu-id="17275-119">**Suggerimento importante: per un aggiornamento sul posto in cui vengono migrate le applicazioni e i dati in Windows 10, è necessario avviare il processo all'interno di una sessione che esegue Windows 7. L'avvio dell'installazione di file multimediali da un DVD o da un'unità USB non consente di conservare le app e i file, ma verrà eseguita un'installazione pulita di Windows 10.**</span><span class="sxs-lookup"><span data-stu-id="17275-119">**Important tip: For an in-place upgrade where applications and your data are migrated to Window 10, you’ll need to initiate the process from within a running Windows 7 session. Booting to install media from a DVD or USB drive will not give you the option to keep your apps and files, instead it will perform a clean install of Windows 10.**</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-2.png)

> <span data-ttu-id="17275-120">File estratti da una versione ISO per Windows 10 Enterprise 32 bit</span><span class="sxs-lookup"><span data-stu-id="17275-120">Extracted files from a Windows 10 Enterprise 32-bit ISO</span></span>

<span data-ttu-id="17275-121">Nell’ambito della configurazione di Windows 10, si passerà alla procedura guidata dell’installazione e la prima schermata offre un'opzione per scaricare aggiornamenti, driver e funzionalità opzionali.</span><span class="sxs-lookup"><span data-stu-id="17275-121">Within Windows 10 Setup, you will be guided through the installation process and the first screen provides an option to download updates, drivers and optional features.</span></span> <span data-ttu-id="17275-122">Questa opzione è consigliata per assicurare la riuscita dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="17275-122">This is recommended to help ensure success with the upgrade</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-3.png)

> <span data-ttu-id="17275-123">Schermata iniziale della configurazione di Windows 10</span><span class="sxs-lookup"><span data-stu-id="17275-123">Initial Windows 10 Setup screen</span></span>

<span data-ttu-id="17275-124">Una volta applicati gli aggiornamenti, l'installazione di Windows 10 passerà alla fase successiva, selezionare immagine.</span><span class="sxs-lookup"><span data-stu-id="17275-124">Once updates have been applied, Windows 10 Setup will move to the next phase, Select Image.</span></span> <span data-ttu-id="17275-125">Qui è necessario selezionare la propria versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="17275-125">Here, you will need to select your edition of Windows.</span></span> <span data-ttu-id="17275-126">In questo caso, poiché il PC è installato in Windows 7 Enterprise, selezionare Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="17275-126">In this case, since the PC has Windows 7 Enterprise installed, you would select Windows 10 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-4.png)

> <span data-ttu-id="17275-127">Schermata di selezione immagine a 32 bit di Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="17275-127">Windows 10 Enterprise 32-bit image selection screen</span></span>

<span data-ttu-id="17275-128">Nella schermata successiva della configurazione di Windows 10 vengono presentati gli avvisi applicabili e le condizioni di licenza.</span><span class="sxs-lookup"><span data-stu-id="17275-128">In the next screen in Windows 10 Setup, you’re presented with applicable notices and license terms.</span></span> <span data-ttu-id="17275-129">Dopo aver letto e compreso gli avvisi e le condizioni, fare clic su "Accetta" per continuare o "Rifiuta" per annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="17275-129">Once you have read and understand the notices and terms, click “Accept” to continue or “Decline” to cancel.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-5.png)

<span data-ttu-id="17275-130">*Notifiche applicabili e condizioni di licenza per Windows 10*</span><span class="sxs-lookup"><span data-stu-id="17275-130">*Windows 10 Applicable notices and license terms*</span></span>

<span data-ttu-id="17275-131">Ora l'installazione di Windows 10 cercherà altri aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="17275-131">Now Windows 10 Setup will look for additional updates.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-6.png)

<span data-ttu-id="17275-132">*Configurazione di aggiornamenti per Windows 10*</span><span class="sxs-lookup"><span data-stu-id="17275-132">*Windows 10 Setup getting updates*</span></span>

<span data-ttu-id="17275-133">Una volta completata, la configurazione di Windows 10 è pronta per l’installazione e, per impostazione predefinita, è configurata per l'installazione di Windows 10. Inoltre, mantiene installati i file personali e le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="17275-133">Once complete, Windows 10 Setup is ready to install and by default is configured to install Windows 10 and keep your personal files and apps installed.</span></span> <span data-ttu-id="17275-134">Questa è l'opzione consigliata.</span><span class="sxs-lookup"><span data-stu-id="17275-134">This is the recommended option.</span></span> <span data-ttu-id="17275-135">Facendo clic su "Cambia cosa mantenere", sono disponibili altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="17275-135">By clicking, “Change what to keep,” you’ll find additional options.</span></span> <span data-ttu-id="17275-136">In caso contrario scegliere “Installa”.</span><span class="sxs-lookup"><span data-stu-id="17275-136">Otherwise, click “Install.”</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-7.png)

<span data-ttu-id="17275-137">*Opzione predefinita di aggiornamento della configurazione di Windows 10*</span><span class="sxs-lookup"><span data-stu-id="17275-137">*Windows 10 Setup upgrade option default*</span></span>

<span data-ttu-id="17275-138">Se si seleziona "Cambia cosa mantenere", verranno visualizzate le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="17275-138">If you select “Change what to keep”, you’ll be presented with these options:</span></span>

<span data-ttu-id="17275-139">"Mantieni solo i file personali" non sposta le app o le impostazioni installate da Windows 7 a Windows 10.</span><span class="sxs-lookup"><span data-stu-id="17275-139">“Keep personal files only” will not move your installed apps or settings from Windows 7 to Windows 10.</span></span> <span data-ttu-id="17275-140">In alternativa, verranno spostati solo i file e gli account utente in Windows.</span><span class="sxs-lookup"><span data-stu-id="17275-140">Instead it will only move your files and user accounts to Windows.</span></span> <span data-ttu-id="17275-141">Le app dovranno essere reinstallate più avanti con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="17275-141">Apps will need to be reinstalled later with this option.</span></span> <span data-ttu-id="17275-142">Usare questa opzione solo se si è certi di poter reinstallare e configurare le app necessarie dopo l'installazione di Windows, in caso contrario, usare l'opzione predefinita "Mantieni file personali e app".</span><span class="sxs-lookup"><span data-stu-id="17275-142">Only use this option if you are confident you can reinstall and configure the apps you will need after Windows is installed, otherwise stick with the default “Keep personal files and apps” option.</span></span>

<span data-ttu-id="17275-143">"Niente" eliminerà i file, le app e le impostazioni ed eseguirà un'installazione pulita di Windows.</span><span class="sxs-lookup"><span data-stu-id="17275-143">“Nothing” will delete your files, apps and settings and perform a clean install of Windows.</span></span> <span data-ttu-id="17275-144">Usare questa opzione solo se in precedenza è stato eseguito il backup dei dati che si desidera mantenere ed è possibile reinstallare le app.</span><span class="sxs-lookup"><span data-stu-id="17275-144">Use this option only if you have previously backed up the data you want to keep and you are able to reinstall your apps.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-8.png)

<span data-ttu-id="17275-145">*Opzioni per l'installazione di Windows 10*</span><span class="sxs-lookup"><span data-stu-id="17275-145">*Windows 10 Setup installation options*</span></span>

<span data-ttu-id="17275-146">L'installazione di Windows 10 otterrà nuovamente gli aggiornamenti in base alle impostazioni selezionate nella schermata precedente.</span><span class="sxs-lookup"><span data-stu-id="17275-146">Now Windows 10 Setup will get updates again based on what you selected in the previous screen.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-9.png)

<span data-ttu-id="17275-147">*Configurazione di aggiornamenti per Windows 10*</span><span class="sxs-lookup"><span data-stu-id="17275-147">*Windows 10 Setup getting updates*</span></span>

<span data-ttu-id="17275-148">Ora Windows 10 verrà installato per diversi minuti e, se si sceglie di mantenere i file e le app personali, tutto si ritroverà nelle stesse posizioni di file e le app saranno ora disponibili in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="17275-148">Now Windows 10 will install for several minutes and if you chose to keep your personal files and apps, everything will be in the same file locations and your apps will now be available in Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-10.png)

<span data-ttu-id="17275-149">*Stato di installazione di Windows 10*</span><span class="sxs-lookup"><span data-stu-id="17275-149">*Windows 10 installation progress*</span></span>

## 

## <a name="recovery-in-windows-10"></a><span data-ttu-id="17275-150">Ripristino in Windows 10</span><span class="sxs-lookup"><span data-stu-id="17275-150">Recovery in Windows 10</span></span>

<span data-ttu-id="17275-151">Dopo l'installazione di Windows 10, l'opzione di ripristino in Windows 10 consente di ottenere fino a 10 giorni di tempo per tornare a Windows 7.</span><span class="sxs-lookup"><span data-stu-id="17275-151">After Windows 10 is installed, the Recovery option in Windows 10 gives you up to 10 days to go back to Windows 7.</span></span> <span data-ttu-id="17275-152">Questa opzione è utile se il dispositivo o l'app del sistema non funziona correttamente ed è necessario tornare all'installazione precedente di Windows 7.</span><span class="sxs-lookup"><span data-stu-id="17275-152">This is useful if a device or app on your system does not function properly and you need to go back to your previous Windows 7 installation.</span></span> <span data-ttu-id="17275-153">Dopo 10 giorni, per impostazione predefinita, Windows 10 libera lo spazio consumato dai file di ripristino di Windows 7 nell'unità disco rigido ed elimina i file dall'installazione precedente.</span><span class="sxs-lookup"><span data-stu-id="17275-153">After 10 days, by default Windows 10 will free up the space consumed by your Windows 7 recovery files on your hard drive and delete files from the previous installation.</span></span> <span data-ttu-id="17275-154">Anche se Windows 7 dopo il periodo di tempo viene eliminato e non è possibile ripristinare Windows 7, le app e i file personali rimarranno in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="17275-154">Although Windows 7 after this time is deleted and you won’t be able to revert Windows 7, your apps and personal files will remain in Windows 10.</span></span>

<span data-ttu-id="17275-155">Per avviare il processo di ripristino di Windows 7, passare a Impostazioni Ripristino di \>Aggiornamento e sicurezza\>.</span><span class="sxs-lookup"><span data-stu-id="17275-155">To start the Go back to Windows 7 process, navigate to Settings \> Update & Security \> Recovery.</span></span> <span data-ttu-id="17275-156">In tornare a Windows 7 selezionare "Inizia".</span><span class="sxs-lookup"><span data-stu-id="17275-156">Under Go back to Windows 7, select “Get started.”</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-11.png)

<span data-ttu-id="17275-157">*Opzioni di ripristino di Windows 10*</span><span class="sxs-lookup"><span data-stu-id="17275-157">*Windows 10 Recovery options*</span></span>

<span data-ttu-id="17275-158">A questo punto, Windows 10 chiederà il motivo per cui si sta per tornare indietro.</span><span class="sxs-lookup"><span data-stu-id="17275-158">Now, Windows 10 will ask why you are going back.</span></span> <span data-ttu-id="17275-159">Se c'è un motivo tecnico, è utile compilarlo per facilitare la risoluzione e garantire che altre persone possano trarre beneficio da questa esperienza.</span><span class="sxs-lookup"><span data-stu-id="17275-159">If there is a technical reason, this is useful to fill out in order to help drive resolution and ensure others can benefit from your experience.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-12.png)

<span data-ttu-id="17275-160">*Windows 10 che chiede il motivo per cui si tornerà a Windows 7*</span><span class="sxs-lookup"><span data-stu-id="17275-160">*Windows 10 asking why you are going back to Windows 7*</span></span>

<span data-ttu-id="17275-161">In molti casi, la versione di Windows 10 avrà emesso aggiornamenti che possono risolvere i problemi tecnici.</span><span class="sxs-lookup"><span data-stu-id="17275-161">In many cases, your version of Windows 10 will have had updates issued, which may resolve technical issues.</span></span> <span data-ttu-id="17275-162">È consigliabile verificare la disponibilità di aggiornamenti e, se trovati e installati, verificare se il problema è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="17275-162">It is encouraged that you check for updates and if found and installed, then check if that fixes the problems you have experienced.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-13.png)

<span data-ttu-id="17275-163">*Controllare la disponibilità di aggiornamenti per Windows 10*</span><span class="sxs-lookup"><span data-stu-id="17275-163">*Windows 10 Recovery check for updates*</span></span>

<span data-ttu-id="17275-164">Se gli aggiornamenti non consentono di risolvere i problemi ed è necessario tornare all'installazione precedente di Windows 7, è possibile che alcune app debbano essere reinstallate, ad esempio qualsiasi app installata durante il periodo di tempo in cui si è utilizzato Windows 10, e alcune impostazioni potrebbero essere andate perse.</span><span class="sxs-lookup"><span data-stu-id="17275-164">If the updates do not resolve issues and you do need to revert to your previous installation of Windows 7, there is a chance that some apps will need to be reinstalled – such as any app that installed during the time you were running Windows 10 – and some settings may be lost.</span></span> <span data-ttu-id="17275-165">In particolare, i file e i documenti salvati in locale durante l’uso di Windows 10 verranno mantenute e saranno disponibili una volta tornati a Windows 7.</span><span class="sxs-lookup"><span data-stu-id="17275-165">Importantly, files and docs you’ve saved locally while using Windows 10 will remain and be available for you once you’re back in Windows 7.</span></span> 

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-14.png)

<span data-ttu-id="17275-166">*Ripristino di Windows 10: informazioni che è necessario conoscere*</span><span class="sxs-lookup"><span data-stu-id="17275-166">*Windows 10 Recovery: What you need to know*</span></span>

<span data-ttu-id="17275-167">Prima di iniziare, verificare di avere un account locale o di dominio e una password già pronti dall'installazione precedente di Windows 7.</span><span class="sxs-lookup"><span data-stu-id="17275-167">Before you get started, make sure you have a local or domain account and password ready from the previous Windows 7 installation.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-15.png)

<span data-ttu-id="17275-168">*Ripristino di Windows 10 assicurandosi di avere le credenziali di accesso dell'installazione precedente*</span><span class="sxs-lookup"><span data-stu-id="17275-168">*Windows 10 Recovery ensuring you have logon credentials from the previous installation*</span></span>

<span data-ttu-id="17275-169">Da qui è possibile avviare il processo per tornare a Windows 7.</span><span class="sxs-lookup"><span data-stu-id="17275-169">From here you can initiate the process to go back to Windows 7.</span></span> <span data-ttu-id="17275-170">Dopo qualche minuto, il PC si avvierà nuovamente in Windows 7 con la stessa esperienza precedente all’esecuzione dell’aggiornamento a Windows 10.</span><span class="sxs-lookup"><span data-stu-id="17275-170">After a few minutes, your PC will boot back into Windows 7 with the same experience prior to upgrading to Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-16.png)

<span data-ttu-id="17275-171">*Schermata finale di ripristino di Windows 10 prima di tornare in Windows 7*</span><span class="sxs-lookup"><span data-stu-id="17275-171">*Windows 10 Recovery final screen before going back to Windows 7*</span></span>

## <a name="moving-to-windows-10-on-a-new-pc"></a><span data-ttu-id="17275-172">Passaggio a Windows 10 in un nuovo PC</span><span class="sxs-lookup"><span data-stu-id="17275-172">Moving to Windows 10 on a new PC</span></span>

<span data-ttu-id="17275-173">Un'altra opzione consigliata consiste nel passare a Windows 10 in un nuovo PC.</span><span class="sxs-lookup"><span data-stu-id="17275-173">Another recommended option is to move to Windows 10 on a new PC.</span></span> <span data-ttu-id="17275-174">Se si preferisce, è possibile trasferire i file dal vecchio computer tramite il backup di [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10), [Backup e ripristino integrato in Windows](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10), manualmente tramite un [dispositivo di archiviazione esterno](https://support.microsoft.com/it-IT/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10) oppure con strumenti come [Laplink PCmover Express](https://www.microsoft.com/en-us/windows/transfer-your-data).</span><span class="sxs-lookup"><span data-stu-id="17275-174">If this is your preference, you can transfer your files from your old computer using [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10) backup, [Backup and Restore built into Windows](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10), manually using an [external storage device](https://support.microsoft.com/en-us/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10), or tools like [Laplink’s PCmover Express](https://www.microsoft.com/en-us/windows/transfer-your-data).</span></span> <span data-ttu-id="17275-175">Con una di queste opzioni sarà comunque necessario reinstallare le applicazioni obbligatorie non incluse in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="17275-175">With any of these options, you will still need to re-install any required applications not included with Windows 10.</span></span> <span data-ttu-id="17275-176">Per altre informazioni sulle opzioni per lo spostamento manuale da un PC che esegue Windows 7 in un nuovo PC con Windows 10, vedere [passaggio a un PC con Windows 10](https://support.microsoft.com/it-IT/help/4229823?ocid=MoveToWindows10) nel supporto di Windows.</span><span class="sxs-lookup"><span data-stu-id="17275-176">To learn more about your options for manually moving from an existing PC running Windows 7 to a new PC with Windows 10, see [Moving to a Windows 10 PC](https://support.microsoft.com/en-us/help/4229823?ocid=MoveToWindows10) in Windows Support.</span></span>

## <a name="desktop-deployment-centerhttpsakamshowtoshift"></a>[<span data-ttu-id="17275-177">Centro di distribuzione desktop</span><span class="sxs-lookup"><span data-stu-id="17275-177">Desktop Deployment Center</span></span>](https://aka.ms/howtoshift)