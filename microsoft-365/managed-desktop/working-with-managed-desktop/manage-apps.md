---
title: Gestire le app in Microsoft Managed Desktop
description: Informazioni su come aggiornare le app line-of-business distribuite in Microsoft Managed Desktop dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600683"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="6a7ae-104">Gestire le app line-of-business in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="6a7ae-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="6a7ae-105">Esistono due modi per gestire gli aggiornamenti delle app per le app che hai onboardato Microsoft Managed Desktop e distribuite nei dispositivi Microsoft Managed Desktop dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="6a7ae-106">È possibile apportare aggiornamenti delle app Microsoft Managed Desktop portale o Intune.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="6a7ae-107">Aggiornare le app line-of-business in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="6a7ae-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="6a7ae-108">**Per aggiornare le app line-of-business in Microsoft Managed Desktop portal**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="6a7ae-109">Accedi a Microsoft Managed Desktop [di amministrazione](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="6a7ae-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="6a7ae-110">In **Inventario** seleziona **App.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="6a7ae-111">Seleziona l'app che vuoi aggiornare e quindi seleziona **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="6a7ae-112">In **Gestisci** selezionare **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="6a7ae-113">Fai **clic su File del pacchetto** dell'app e quindi cerca di caricare un nuovo file del pacchetto dell'app.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="6a7ae-114">Selezionare **File del pacchetto dell'app**.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-114">Select **App package file**.</span></span>
7. <span data-ttu-id="6a7ae-115">Seleziona l'icona della cartella e passa al percorso del file dell'app aggiornato.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="6a7ae-116">Seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-116">Select **Open**.</span></span> <span data-ttu-id="6a7ae-117">Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="6a7ae-118">Verifica che **la versione dell'app** rifletta il pacchetto dell'app aggiornato.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="6a7ae-119">L'app aggiornata verrà distribuita nei dispositivi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="6a7ae-120">Aggiornare le app line-of-business in Intune</span><span class="sxs-lookup"><span data-stu-id="6a7ae-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="6a7ae-121">**Per aggiornare le app line-of-business in Intune**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="6a7ae-122">Accedere al [portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6a7ae-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="6a7ae-123">Selezionare **Tutti i servizi**  >  **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="6a7ae-124">Intune è nella **sezione Monitoraggio e** gestione.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="6a7ae-125">Selezionare **App client > app**.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="6a7ae-126">Trova e seleziona la tua app nell'elenco delle app.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="6a7ae-127">Nel pannello **Panoramica** selezionare **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="6a7ae-128">Selezionare **File del pacchetto dell'app**.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-128">Select **App package file**.</span></span>
7. <span data-ttu-id="6a7ae-129">Seleziona l'icona della cartella e passa al percorso del file dell'app aggiornato.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="6a7ae-130">Seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-130">Select **Open**.</span></span> <span data-ttu-id="6a7ae-131">Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="6a7ae-132">Verifica che **la versione dell'app** rifletta il pacchetto dell'app aggiornato.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="6a7ae-133">Eseguire il rollback di un'app a una versione precedente</span><span class="sxs-lookup"><span data-stu-id="6a7ae-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="6a7ae-134">Se viene rilevato un errore quando viene distribuita una nuova versione di un'app, puoi eseguire il rollback a una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="6a7ae-135">Il processo descritto qui è per le app in cui il tipo è elencato come **Windows app line-of-business MSI** o app Windows **(Win 32) - anteprima**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="6a7ae-136">**Per eseguire il rollback di un'app line-of-business a una versione precedente**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="6a7ae-137">Accedi a Microsoft Managed Desktop [di amministrazione](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="6a7ae-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="6a7ae-138">In **Inventario** seleziona **App.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="6a7ae-139">Seleziona l'app di cui vuoi eseguire il rollback e quindi seleziona **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="6a7ae-140">In **Gestisci** selezionare **Proprietà.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="6a7ae-141">Per **Windows app line-of-business MSI,** selezionare Informazioni sull'app **e** quindi in Ignora versione **app** selezionare **Sì.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="6a7ae-142">Per **Windows app (Win 32) -** anteprima delle app, seleziona Informazioni **app,** seleziona **Regole** di rilevamento e quindi seleziona **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="6a7ae-143">Se è presente una regola MSI, verificare che il controllo della versione del prodotto **MSI** sia impostato su **No**.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="6a7ae-144">Upload una versione precedente del file di [origine dell'app](../get-started/deploy-apps.md) per Microsoft Managed Desktop portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

