---
title: Gestione le esclusioni delle cartelle di automazione
description: Aggiungi esclusioni di cartelle di automazione per controllare i file esclusi da un'indagine automatizzata.
keywords: gestire, automazione, esclusione, bloccare, pulire, dannoso
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185838"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="d5c1a-104">Gestione le esclusioni delle cartelle di automazione</span><span class="sxs-lookup"><span data-stu-id="d5c1a-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d5c1a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d5c1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d5c1a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d5c1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d5c1a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5c1a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d5c1a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d5c1a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d5c1a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="d5c1a-110">Le esclusioni delle cartelle di automazione consentono di specificare le cartelle che verranno ignorate dall'analisi automatica.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="d5c1a-111">È possibile controllare gli attributi seguenti relativi alla cartella che si desidera ignorare:</span><span class="sxs-lookup"><span data-stu-id="d5c1a-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="d5c1a-112">Cartelle</span><span class="sxs-lookup"><span data-stu-id="d5c1a-112">Folders</span></span> 
- <span data-ttu-id="d5c1a-113">Estensioni dei file</span><span class="sxs-lookup"><span data-stu-id="d5c1a-113">Extensions of the files</span></span>
- <span data-ttu-id="d5c1a-114">Nomi di file</span><span class="sxs-lookup"><span data-stu-id="d5c1a-114">File names</span></span>


<span data-ttu-id="d5c1a-115">**Cartelle**</span><span class="sxs-lookup"><span data-stu-id="d5c1a-115">**Folders**</span></span><br>
<span data-ttu-id="d5c1a-116">È possibile specificare una cartella e le relative sottocartelle da ignorare.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="d5c1a-117">Al momento, l'uso di caratteri jolly come modo per escludere i file in una directory non è ancora supportato.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="d5c1a-118">**Estensioni**</span><span class="sxs-lookup"><span data-stu-id="d5c1a-118">**Extensions**</span></span><br>
<span data-ttu-id="d5c1a-119">È possibile specificare le estensioni da escludere in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="d5c1a-120">Le estensioni sono un modo per impedire a un utente malintenzionato di usare una cartella esclusa per nascondere un exploit.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="d5c1a-121">Le estensioni definiscono in modo esplicito i file da ignorare.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="d5c1a-122">**Nomi di file**</span><span class="sxs-lookup"><span data-stu-id="d5c1a-122">**File names**</span></span><br>
<span data-ttu-id="d5c1a-123">È possibile specificare i nomi di file che si desidera escludere in una directory specifica.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="d5c1a-124">I nomi sono un modo per impedire a un utente malintenzionato di usare una cartella esclusa per nascondere un exploit.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="d5c1a-125">I nomi definiscono in modo esplicito i file da ignorare.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="d5c1a-126">Aggiungere un'esclusione di cartella di automazione</span><span class="sxs-lookup"><span data-stu-id="d5c1a-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="d5c1a-127">Nel riquadro di spostamento selezionare **Impostazioni**  >  **cartelle di automazione**.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="d5c1a-128">Fare **clic su Esclusione nuova cartella.**</span><span class="sxs-lookup"><span data-stu-id="d5c1a-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="d5c1a-129">Immetti i dettagli della cartella:</span><span class="sxs-lookup"><span data-stu-id="d5c1a-129">Enter the folder details:</span></span>

    - <span data-ttu-id="d5c1a-130">Cartella</span><span class="sxs-lookup"><span data-stu-id="d5c1a-130">Folder</span></span>
    - <span data-ttu-id="d5c1a-131">Estensioni</span><span class="sxs-lookup"><span data-stu-id="d5c1a-131">Extensions</span></span>
    - <span data-ttu-id="d5c1a-132">Nomi di file</span><span class="sxs-lookup"><span data-stu-id="d5c1a-132">File names</span></span>
    - <span data-ttu-id="d5c1a-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5c1a-133">Description</span></span>
    

4. <span data-ttu-id="d5c1a-134">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="d5c1a-135">I comandi di Live Response per raccogliere o esaminare i file esclusi avranno esito negativo con l'errore: "File escluso".</span><span class="sxs-lookup"><span data-stu-id="d5c1a-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="d5c1a-136">Inoltre, le indagini automatizzate ignoreranno gli elementi esclusi.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="d5c1a-137">Modificare l'esclusione di una cartella di automazione</span><span class="sxs-lookup"><span data-stu-id="d5c1a-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="d5c1a-138">Nel riquadro di spostamento selezionare **Impostazioni**  >  **cartelle di automazione**.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="d5c1a-139">Fare **clic su** Modifica nell'esclusione della cartella.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="d5c1a-140">Aggiornare i dettagli della regola e fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="d5c1a-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="d5c1a-141">Rimuovere un'esclusione di cartelle di automazione</span><span class="sxs-lookup"><span data-stu-id="d5c1a-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="d5c1a-142">Nel riquadro di spostamento selezionare **Impostazioni**  >  **cartelle di automazione**.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="d5c1a-143">Fare clic **su Rimuovi esclusione.**</span><span class="sxs-lookup"><span data-stu-id="d5c1a-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="d5c1a-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d5c1a-144">Related topics</span></span>
- [<span data-ttu-id="d5c1a-145">Gestire gli elenchi di automazione consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="d5c1a-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="d5c1a-146">Gestire il caricamento di file di automazione</span><span class="sxs-lookup"><span data-stu-id="d5c1a-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
