---
title: Caricare i dati non di Office 365 in Evidence
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
ms.openlocfilehash: ee1e6f8a064567126d75b099cc3003e8a4d6a020
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083836"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="42617-102">Caricare i dati non di Office 365 in Evidence</span><span class="sxs-lookup"><span data-stu-id="42617-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="42617-103">Non tutti i documenti che potrebbe essere necessario analizzare con Office 365 Advanced eDiscovery vivranno in Office 365.</span><span class="sxs-lookup"><span data-stu-id="42617-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="42617-104">Con la caratteristica di importazione di contenuto non Office 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Office 365 in un working set, in modo da essere analizzati con Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="42617-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="42617-105">In questa procedura viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="42617-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="42617-106">Advanced eDiscovery richiede un Office 365 E3 con il componente aggiuntivo per la conformità avanzato o un abbonamento E5 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="42617-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="42617-107">Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile iscriversi per una versione di valutazione di Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="42617-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="42617-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="42617-108">Before you begin</span></span>
<span data-ttu-id="42617-109">Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:</span><span class="sxs-lookup"><span data-stu-id="42617-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="42617-110">Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5.</span><span class="sxs-lookup"><span data-stu-id="42617-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="42617-111">Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="42617-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="42617-112">Un caso di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="42617-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="42617-113">Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias @ NomeDominio* .</span><span class="sxs-lookup"><span data-stu-id="42617-113">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* .</span></span> <span data-ttu-id="42617-114">L' *alias @ DomainName* deve essere Users Office 365 alias and Domain.</span><span class="sxs-lookup"><span data-stu-id="42617-114">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="42617-115">È possibile raccogliere tutte le cartelle *alias @ DomainName* in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="42617-115">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="42617-116">La cartella radice può contenere solo le cartelle *alias @ DomainName* , non devono essere presenti file liberi nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="42617-116">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="42617-117">Un account che sia uno eDiscovery Manager o eDiscovery Administrator Microsoft Azure Storage Tools installato su un computer che ha accesso alla struttura di cartelle di contenuto non Office 365.</span><span class="sxs-lookup"><span data-stu-id="42617-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="42617-118">Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="42617-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="42617-119">Caricare il contenuto non Office 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="42617-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="42617-120">Come eDiscovery Manager o amministratore di eDiscovery, aprire Advanced eDiscovery, quindi il caso in cui i dati non di Office 365 verranno caricati.</span><span class="sxs-lookup"><span data-stu-id="42617-120">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="42617-121">Fare clic sulla scheda **working set** , quindi selezionare il working set a cui si desidera caricare i dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="42617-121">Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="42617-122">Se non è stato ancora creato un working set, è possibile farlo adesso.</span><span class="sxs-lookup"><span data-stu-id="42617-122">If you have not already created a working set, you can do so now.</span></span>  <span data-ttu-id="42617-123">Infine, fare clic su **Gestisci set di lavoro** e quindi **visualizzare i caricamenti** nella sezione dati non di Office 365</span><span class="sxs-lookup"><span data-stu-id="42617-123">Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="42617-124">Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="42617-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Caricare file](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="42617-126">Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.</span><span class="sxs-lookup"><span data-stu-id="42617-126">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="42617-127">Dopo la preparazione, fare clic sul pulsante **Avanti: carica file** .</span><span class="sxs-lookup"><span data-stu-id="42617-127">Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![Importazione non Office 365-preparazione](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="42617-129">Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non di Office 365 pianificati per l'importazione.</span><span class="sxs-lookup"><span data-stu-id="42617-129">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="42617-130">L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="42617-130">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="42617-131">Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="42617-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="42617-132">Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** .</span><span class="sxs-lookup"><span data-stu-id="42617-132">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="42617-133">Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="42617-133">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="42617-134">I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="42617-134">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Importazione/caricamento di file non di Office 365](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Non Office 365 Import-AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="42617-137">Infine, tornare alla conformità & di sicurezza e fare clic sul pulsante **Avanti: elabora file** .</span><span class="sxs-lookup"><span data-stu-id="42617-137">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="42617-138">Verrà avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.</span><span class="sxs-lookup"><span data-stu-id="42617-138">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="42617-139">È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completato, i nuovi file saranno disponibili nel working set.</span><span class="sxs-lookup"><span data-stu-id="42617-139">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.</span></span>  <span data-ttu-id="42617-140">Dopo aver completato l'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="42617-140">Once processing is complete, you can dismiss the wizard.</span></span>

![File del processo di importazione non Office 365](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

