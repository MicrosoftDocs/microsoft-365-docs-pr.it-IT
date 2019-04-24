---
title: Gestire le app in Microsoft Managed Desktop
description: Informazioni su come aggiornare le app line-of-business distribuite ai dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ce2765ef2ab176dc5d9a1d41db7e26549b007d79
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285946"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="5a92a-104">Gestire le app line-of-business in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5a92a-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="5a92a-105">Esistono due modi per gestire gli aggiornamenti delle app per le app che sono state onboarded to Microsoft Managed Desktop e distribuite ai dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5a92a-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="5a92a-106">È possibile rendere gli aggiornamenti delle app in Microsoft Managed Desktop Portal o Intune.</span><span class="sxs-lookup"><span data-stu-id="5a92a-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="5a92a-107">Aggiornare le app line-of-business in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5a92a-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="5a92a-108">**Per aggiornare le app line-of-business in Microsoft Managed Desktop Portal**</span><span class="sxs-lookup"><span data-stu-id="5a92a-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="5a92a-109">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="5a92a-109">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="5a92a-110">In **inventario**, selezionare **app**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="5a92a-111">Selezionare l'app che si desidera aggiornare e quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="5a92a-112">In **Gestisci**selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="5a92a-113">Fare clic su **file del pacchetto di app**e quindi selezionare per caricare un nuovo file del pacchetto di app.</span><span class="sxs-lookup"><span data-stu-id="5a92a-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="5a92a-114">Selezionare il **file del pacchetto di app**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-114">Select **App package file**.</span></span>
7. <span data-ttu-id="5a92a-115">Selezionare l'icona della cartella e passare al percorso del file dell'app aggiornato.</span><span class="sxs-lookup"><span data-stu-id="5a92a-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="5a92a-116">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-116">Select **Open**.</span></span> <span data-ttu-id="5a92a-117">Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5a92a-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="5a92a-118">Verificare che la **versione dell'app** rifletta il pacchetto di App aggiornato.</span><span class="sxs-lookup"><span data-stu-id="5a92a-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="5a92a-119">L'app aggiornata verrà distribuita nei dispositivi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5a92a-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="5a92a-120">Aggiornare le app line-of-business in Intune</span><span class="sxs-lookup"><span data-stu-id="5a92a-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="5a92a-121">**Per aggiornare le app line-of-business in Intune**</span><span class="sxs-lookup"><span data-stu-id="5a92a-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="5a92a-122">Accedere al [portale di Azure](https://azure.portal.com).</span><span class="sxs-lookup"><span data-stu-id="5a92a-122">Sign in to [Azure portal](https://azure.portal.com).</span></span>
2. <span data-ttu-id="5a92a-123">Selezionare **tutti i servizi** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="5a92a-124">Intune si trova nella sezione **Monitoring + Management** .</span><span class="sxs-lookup"><span data-stu-id="5a92a-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="5a92a-125">Selezionare app **client Apps >**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="5a92a-126">Individuare e selezionare l'app nell'elenco delle app.</span><span class="sxs-lookup"><span data-stu-id="5a92a-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="5a92a-127">Nel pannello **Panoramica** , selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="5a92a-128">Selezionare il **file del pacchetto di app**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-128">Select **App package file**.</span></span>
7. <span data-ttu-id="5a92a-129">Selezionare l'icona della cartella e passare al percorso del file dell'app aggiornato.</span><span class="sxs-lookup"><span data-stu-id="5a92a-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="5a92a-130">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-130">Select **Open**.</span></span> <span data-ttu-id="5a92a-131">Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5a92a-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="5a92a-132">Verificare che la **versione dell'app** rifletta il pacchetto di App aggiornato.</span><span class="sxs-lookup"><span data-stu-id="5a92a-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="5a92a-133">Eseguire il rollback di un'app a una versione precedente</span><span class="sxs-lookup"><span data-stu-id="5a92a-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="5a92a-134">Se viene rilevato un errore quando viene distribuita una nuova versione di un'app, è possibile eseguire il rollback a una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="5a92a-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="5a92a-135">Il processo qui descritto è per le app in cui il tipo è elencato come **app line-of-business MSI di Windows** o **app windows (Win 32)-Preview**</span><span class="sxs-lookup"><span data-stu-id="5a92a-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="5a92a-136">**Per eseguire il rollback di un'app line-of-business a una versione precedente**</span><span class="sxs-lookup"><span data-stu-id="5a92a-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="5a92a-137">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="5a92a-137">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="5a92a-138">In **inventario**, selezionare **app**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="5a92a-139">Seleziona l'app di cui hai bisogno per eseguire il rollback e quindi seleziona **modifica**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="5a92a-140">In **Gestisci**selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="5a92a-141">Per le **app di applicazioni line-of-business MSI di Windows** , selezionare **informazioni sull'app**e quindi in **Ignora versione app**selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="5a92a-142">Per **app Windows (Win 32)-** app di anteprima, **Seleziona informazioni sull'app**, seleziona **regole di rilevamento**e quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="5a92a-143">Se è presente una regola MSI, verificare che il **controllo della versione del prodotto MSI** sia impostato su **No**.</span><span class="sxs-lookup"><span data-stu-id="5a92a-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="5a92a-144">[Caricare una versione precedente del file di origine dell'applicazione](../get-started/deploy-apps.md) nel portale di amministrazione di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5a92a-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

