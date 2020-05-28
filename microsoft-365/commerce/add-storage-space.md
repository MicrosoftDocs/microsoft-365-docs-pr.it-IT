---
title: Aggiungere spazio di archiviazione per l'abbonamento
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEU150
- GEA150
- GSP150
ms.assetid: 96ea3533-de64-4b01-839a-c560875a662c
description: Informazioni su come aggiungere e ridurre l'archiviazione dei file nell'abbonamento a Microsoft 365. Con un'ulteriore archiviazione dei file, è possibile archiviare più contenuto in SharePoint Online e OneDrive.
ms.openlocfilehash: f31495127feb345cccdc792c60333f5fc0c7cc6f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402679"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="90933-104">Aggiungere spazio di archiviazione per l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="90933-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="90933-105">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="90933-105">The admin center is changing.</span></span> <span data-ttu-id="90933-106">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="90933-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="90933-107">Se lo spazio di archiviazione per le raccolte di siti di SharePoint Online sta per esaurirsi, è possibile aggiungere altro spazio all'abbonamento, se il piano è idoneo.</span><span class="sxs-lookup"><span data-stu-id="90933-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="90933-108">Se l' **Archivio di file aggiuntivo di Office 365** non è presente nell'elenco dei componenti aggiuntivi disponibili, significa che il piano non è idoneo.</span><span class="sxs-lookup"><span data-stu-id="90933-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="90933-109">Per ulteriori informazioni, vedere [è il mio piano idoneo?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="90933-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="90933-110">Visualizzazione dello spazio di archiviazione disponibile</span><span class="sxs-lookup"><span data-stu-id="90933-110">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="90933-111">Passare alla [pagina Siti attivi della nuova interfaccia di amministrazione di SharePoint](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true) e accedere con un account dotato di [autorizzazioni di amministratore](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="90933-111">Go to the [Active sites page of the new SharePoint admin center](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true), and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="90933-112">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione utilizzata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="90933-112">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="90933-113">Se nell'organizzazione è stata configurata la multi-Geo in Office 365, la barra Visualizza anche la quantità di spazio di archiviazione utilizzata in tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="90933-113">(If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.)</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="90933-114">Accedere https://portal.office.de come amministratore globale o di SharePoint e quindi selezionare il riquadro amministratore per aprire l'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="90933-114">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="90933-115">Se viene visualizzato un messaggio in cui non si dispone dell'autorizzazione per accedere alla pagina, non si dispone delle autorizzazioni di amministratore Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="90933-115">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="90933-116">Nel riquadro sinistro, in interfaccia di **Amministrazione**, selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="90933-116">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="90933-117">Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="90933-117">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="90933-118">Nel riquadro a sinistra dell'interfaccia di amministrazione di SharePoint selezionare **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="90933-118">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="90933-119">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione utilizzata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="90933-119">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="90933-120">Accedere https://login.partner.microsoftonline.cn/ come amministratore globale o di SharePoint e quindi selezionare il riquadro amministratore per aprire l'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="90933-120">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="90933-121">Se viene visualizzato un messaggio in cui non si dispone dell'autorizzazione per accedere alla pagina, non si dispone delle autorizzazioni di amministratore Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="90933-121">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="90933-122">Nel riquadro sinistro, in interfaccia di **Amministrazione**, selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="90933-122">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="90933-123">Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="90933-123">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="90933-124">Nel riquadro a sinistra dell'interfaccia di amministrazione di SharePoint selezionare **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="90933-124">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="90933-125">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione utilizzata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="90933-125">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

::: moniker-end

![Barra di archiviazione nella pagina siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

> [!NOTE]
> <span data-ttu-id="90933-127">Lo spazio di archiviazione utilizzato non include le modifiche apportate nelle ultime 24-48 ore.</span><span class="sxs-lookup"><span data-stu-id="90933-127">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="90933-128">Dopo aver identificato la quantità di spazio di archiviazione in uso, è possibile aggiungerne altro o rimuoverlo dall'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="90933-128">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="90933-129">Per sapere quanto costerà aggiungere spazio di archiviazione, seguire i passaggi descritti in questo articolo ed esaminare le informazioni sui prezzi prima di acquistare.</span><span class="sxs-lookup"><span data-stu-id="90933-129">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="90933-130">Per informazioni sull'impostazione dei limiti di archiviazione delle raccolte siti, vedere [gestire i limiti di archiviazione delle raccolte siti](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="90933-130">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="90933-131">Aggiungere spazio di archiviazione all'abbonamento</span><span class="sxs-lookup"><span data-stu-id="90933-131">Add storage to your subscription</span></span>

<span data-ttu-id="90933-132">Se non è stato ancora acquistato un ulteriore spazio di archiviazione per l'abbonamento, è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="90933-132">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="90933-133">Nell'interfaccia di amministrazione, andare alla **Billing** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servizi di acquisto</a> per la fatturazione.</span><span class="sxs-lookup"><span data-stu-id="90933-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

2. <span data-ttu-id="90933-134">Nella parte inferiore della pagina **acquisto servizi** selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="90933-134">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>

3. <span data-ttu-id="90933-135">Selezionare **Office 365 extra file storage**.</span><span class="sxs-lookup"><span data-stu-id="90933-135">Select **Office 365 Extra File Storage**.</span></span>

4. <span data-ttu-id="90933-136">Nella pagina **Office 365 extra file storage** , se visualizzata, scegliere la sottoscrizione di base e quindi immettere il numero di gigabyte di spazio di archiviazione che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="90933-136">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>

5. <span data-ttu-id="90933-137">Selezionare **Estrai ora**.</span><span class="sxs-lookup"><span data-stu-id="90933-137">Select **Check out now**.</span></span>

6. <span data-ttu-id="90933-138">In **questa** pagina, verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="90933-138">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="90933-139">Nella pagina **ordine completo** verificare il totale.</span><span class="sxs-lookup"><span data-stu-id="90933-139">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="90933-140">Se è necessario apportare modifiche, selezionare **modifica ordine**.</span><span class="sxs-lookup"><span data-stu-id="90933-140">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="90933-141">Se l'ordine richiede una verifica del credito, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="90933-141">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="90933-142">Al termine, selezionare **Ordina per** \> **accedere a Home page di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="90933-142">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="90933-143">Nell'interfaccia di amministrazione, andare alla pagina **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">abbonamenti</a> di fatturazione.  </span><span class="sxs-lookup"><span data-stu-id="90933-143">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="90933-144">Nella pagina **abbonamenti** scegliere la sottoscrizione a cui si desidera aggiungere spazio di archiviazione, quindi selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="90933-144">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="90933-146">Se i **componenti aggiuntivi**non sono visibili e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="90933-146">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="90933-147">Selezionare **acquista componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="90933-147">Select **Buy add-ons**.</span></span>

    ![Acquistare un collegamento per i componenti aggiuntivi nella pagina abbonamenti dell'interfaccia di amministrazione.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="90933-149">Nella pagina **acquisto servizi** , passare il mouse o toccare **Office 365 extra file storage**, quindi scegliere **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="90933-149">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="90933-150">Immettere il numero di licenze utente necessarie e, se visualizzato, scegliere una sottoscrizione di base.</span><span class="sxs-lookup"><span data-stu-id="90933-150">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="90933-151">Selezionare **Estrai ora**.</span><span class="sxs-lookup"><span data-stu-id="90933-151">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="90933-152">In **questa** pagina, verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="90933-152">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="90933-153">Nella pagina **ordine completo** selezionare **luogo ordine**.</span><span class="sxs-lookup"><span data-stu-id="90933-153">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="90933-154">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="90933-154">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="90933-155">Nella pagina **abbonamenti** scegliere la sottoscrizione a cui si desidera aggiungere spazio di archiviazione, quindi selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="90933-155">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="90933-157">Se i **componenti aggiuntivi**non sono visibili e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="90933-157">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="90933-158">Selezionare **acquista componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="90933-158">Select **Buy add-ons**.</span></span>

    ![Acquistare un collegamento per i componenti aggiuntivi nella pagina abbonamenti dell'interfaccia di amministrazione.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="90933-160">Nella pagina **acquisto servizi** , passare il mouse o toccare **Office 365 extra file storage**, quindi scegliere **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="90933-160">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="90933-161">Immettere il numero di licenze utente necessarie e, se visualizzato, scegliere una sottoscrizione di base.</span><span class="sxs-lookup"><span data-stu-id="90933-161">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="90933-162">Selezionare **Estrai ora**.</span><span class="sxs-lookup"><span data-stu-id="90933-162">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="90933-163">In **questa** pagina, verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="90933-163">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="90933-164">Nella pagina **ordine completo** selezionare **luogo ordine**.</span><span class="sxs-lookup"><span data-stu-id="90933-164">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="90933-165">Aumentare o diminuire lo spazio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="90933-165">Increase or decrease storage</span></span>

<span data-ttu-id="90933-166">Se si è già acquistato un file di archiviazione supplementare tramite il componente aggiuntivo di **archiviazione file aggiuntivo di Office 365** , è possibile utilizzare questi passaggi per aumentare o diminuire lo spazio di archiviazione aggiuntivo per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="90933-166">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="90933-167">È possibile ridurre lo spazio di archiviazione a un minimo di 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="90933-167">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="90933-168">Per rimuovere tutto lo spazio di archiviazione aggiuntivo, è necessario [contattare il supporto tecnico](../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="90933-168">To remove all of the extra storage space, you need to [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="90933-169">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="90933-169">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="90933-170">Scegliere l'abbonamento che contiene il componente aggiuntivo di **archiviazione file aggiuntivo di Office 365** .</span><span class="sxs-lookup"><span data-stu-id="90933-170">Choose the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>

3. <span data-ttu-id="90933-171">Selezionare **componenti**aggiuntivi, quindi scegliere **Cambia quantità**.</span><span class="sxs-lookup"><span data-stu-id="90933-171">Select **Add-ons**, then choose **Change quantity**.</span></span>

4. <span data-ttu-id="90933-172">Nel riquadro **Aggiungi/Rimuovi Gigabyte** , immettere i gigabyte totali desiderati per l'abbonamento, quindi selezionare **Invia modifica**.</span><span class="sxs-lookup"><span data-stu-id="90933-172">In the **Add/Remove gigabytes** pane, enter the total gigabytes you want for the subscription, then select **Submit change**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="90933-173">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="90933-173">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="90933-174">Nella pagina **abbonamenti** selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="90933-174">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="90933-176">Se i **componenti aggiuntivi**non sono visibili e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="90933-176">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="90933-177">In **Office 365 extra file storage**selezionare **Change Quantity**.</span><span class="sxs-lookup"><span data-stu-id="90933-177">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Collegamento Cambio di quantità.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="90933-179">Nel riquadro a destra, immettere il numero totale di Gigabyte necessari, quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="90933-179">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="90933-180">Ad esempio, se attualmente si hanno 200 gigabyte di spazio di archiviazione file aggiuntivo ma ne servono solo 100, immettere **100** nella casella.</span><span class="sxs-lookup"><span data-stu-id="90933-180">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="90933-181">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="90933-181">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="90933-182">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="90933-182">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="90933-183">Nella pagina **abbonamenti** selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="90933-183">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="90933-185">Se i **componenti aggiuntivi**non sono visibili e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="90933-185">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="90933-186">In **Office 365 extra file storage**selezionare **Change Quantity**.</span><span class="sxs-lookup"><span data-stu-id="90933-186">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Collegamento Cambio di quantità.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="90933-188">Nel riquadro a destra, immettere il numero totale di Gigabyte necessari, quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="90933-188">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="90933-189">Ad esempio, se attualmente si hanno 200 gigabyte di spazio di archiviazione file aggiuntivo ma ne servono solo 100, immettere **100** nella casella.</span><span class="sxs-lookup"><span data-stu-id="90933-189">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="90933-190">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="90933-190">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="90933-191">Quali piani sono idonei per Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="90933-191">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="90933-192">Office 365 Extra File Storage è disponibile per gli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="90933-192">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="90933-193">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="90933-193">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="90933-194">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="90933-194">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="90933-195">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="90933-195">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="90933-196">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="90933-196">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="90933-197">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="90933-197">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="90933-198">Office per il Web con SharePoint piano 1</span><span class="sxs-lookup"><span data-stu-id="90933-198">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="90933-199">Office per il Web con SharePoint piano 2</span><span class="sxs-lookup"><span data-stu-id="90933-199">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="90933-200">SharePoint Online Piano 1</span><span class="sxs-lookup"><span data-stu-id="90933-200">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="90933-201">SharePoint Online Piano 2</span><span class="sxs-lookup"><span data-stu-id="90933-201">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="90933-202">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="90933-202">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="90933-203">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="90933-203">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="90933-204">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="90933-204">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="90933-205">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="90933-205">Microsoft 365 E3</span></span>

- <span data-ttu-id="90933-206">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="90933-206">Microsoft 365 E5</span></span>

- <span data-ttu-id="90933-207">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="90933-207">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="90933-208">Office 365 è disponibile anche per i piani GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="90933-208">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>
