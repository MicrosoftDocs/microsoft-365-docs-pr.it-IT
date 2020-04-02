---
title: Caricare i dati non di Office 365 in Evidence
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
description: ''
ms.openlocfilehash: 7d2f4fe685e17690b76124517468e0eceec8b414
ms.sourcegitcommit: 825037f166eea3ba70f8980cedc5492f90c1cc56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "43097219"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="b9e35-102">Caricare i dati non di Office 365 in Evidence</span><span class="sxs-lookup"><span data-stu-id="b9e35-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="b9e35-103">Non tutti i documenti che potrebbe essere necessario analizzare in un'indagine dati saranno disponibili in Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9e35-103">Not all documents that you may need to analyze in a data investigation will be located in Office 365.</span></span> <span data-ttu-id="b9e35-104">Con la funzionalità di importazione di contenuto non Office 365 è possibile caricare documenti che non risiedono in Office 365 in elementi di prova in modo che possano essere analizzati in un'analisi dei dati.</span><span class="sxs-lookup"><span data-stu-id="b9e35-104">With the Non-Office 365 content import feature you can upload documents that don't live in Office 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b9e35-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b9e35-105">Before you begin</span></span>

<span data-ttu-id="b9e35-106">Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:</span><span class="sxs-lookup"><span data-stu-id="b9e35-106">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="b9e35-107">Un abbonamento A Microsoft 365 o Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b9e35-107">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="b9e35-108">Tutti gli utenti di interesse di cui verrà caricato il contenuto non di Office 365 devono disporre della licenza di componente aggiuntivo E5 o E5.</span><span class="sxs-lookup"><span data-stu-id="b9e35-108">All people of interest whose non-Office 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="b9e35-109">Un caso di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="b9e35-109">An existing eDiscovery case.</span></span>

- <span data-ttu-id="b9e35-110">Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="b9e35-110">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="b9e35-111">I *alias@domainname* devono essere utenti di Office 365 alias e Domain.</span><span class="sxs-lookup"><span data-stu-id="b9e35-111">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="b9e35-112">È possibile raccogliere tutte le cartelle di *alias@domainname* in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="b9e35-112">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="b9e35-113">La cartella radice può contenere solo le cartelle *alias@domainname* , non devono essere presenti file liberi nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="b9e35-113">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="b9e35-114">Un account che sia uno eDiscovery Manager o eDiscovery Administrator Microsoft Azure Storage Tools installato su un computer che ha accesso alla struttura di cartelle di contenuto non Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9e35-114">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="b9e35-115">Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="b9e35-115">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a><span data-ttu-id="b9e35-116">Caricare il contenuto non Office 365 in un'indagine sui dati</span><span class="sxs-lookup"><span data-stu-id="b9e35-116">Upload non-Office 365 content in to a data investigation</span></span>

1. <span data-ttu-id="b9e35-117">Aprire **indagini sui dati** e passare all'analisi in cui verranno caricati i dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9e35-117">Open **Data Investigations** and go to the investigation that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="b9e35-118">Fare clic sulla scheda **Evidence** , quindi selezionare il set di prove su cui si desidera caricare i dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9e35-118">Click the **Evidence** tab, then select the evidence set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="b9e35-119">Se non è stato ancora creato un set di prove, è possibile farlo adesso.</span><span class="sxs-lookup"><span data-stu-id="b9e35-119">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="b9e35-120">Infine, fare clic su **Gestisci elementi di prova** e quindi **Visualizza i caricamenti** nella sezione dati non di Office 365</span><span class="sxs-lookup"><span data-stu-id="b9e35-120">Finally, click **Manage evidence** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="b9e35-121">Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9e35-121">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="b9e35-123">Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.</span><span class="sxs-lookup"><span data-stu-id="b9e35-123">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="b9e35-124">Al termine della preparazione, fare clic sul pulsante **Avanti: carica file** .</span><span class="sxs-lookup"><span data-stu-id="b9e35-124">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Prepararsi per l'importazione di dati non di Office 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="b9e35-126">Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non di Office 365 pianificati per l'importazione.</span><span class="sxs-lookup"><span data-stu-id="b9e35-126">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="b9e35-127">L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="b9e35-127">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="b9e35-128">Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="b9e35-128">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="b9e35-129">Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** .</span><span class="sxs-lookup"><span data-stu-id="b9e35-129">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="b9e35-130">Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="b9e35-130">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="b9e35-131">I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="b9e35-131">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Caricare i file per l'importazione di dati non di Office 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Utilizzo di AzCopy per importare dati non di Office 365](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="b9e35-134">Infine, tornare alla conformità & di sicurezza e fare clic sul pulsante **Avanti: elabora file** .</span><span class="sxs-lookup"><span data-stu-id="b9e35-134">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="b9e35-135">Questo avvia l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.</span><span class="sxs-lookup"><span data-stu-id="b9e35-135">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="b9e35-136">È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completati, i nuovi file sono disponibili nel set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="b9e35-136">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="b9e35-137">Al termine dell'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b9e35-137">After processing is complete, you can dismiss the wizard.</span></span>

![File di processo di importazione non Office 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

