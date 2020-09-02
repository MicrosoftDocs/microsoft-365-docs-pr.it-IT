---
title: Aggiungere spazio di archiviazione per l'abbonamento
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- MET150
description: Informazioni su come aggiungere e ridurre l'archiviazione dei file nell'abbonamento a Microsoft 365. Con un'ulteriore archiviazione dei file, è possibile archiviare più contenuto in SharePoint Online e OneDrive.
ms.date: ''
ms.openlocfilehash: 7f9973054bfe97beae36e28b73a3eb2025a13e73
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324469"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="1fa14-104">Aggiungere spazio di archiviazione per l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="1fa14-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1fa14-105">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="1fa14-105">The admin center is changing.</span></span> <span data-ttu-id="1fa14-106">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="1fa14-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1fa14-107">Se lo spazio di archiviazione per le raccolte di siti di SharePoint Online sta per esaurirsi, è possibile aggiungere altro spazio all'abbonamento, se il piano è idoneo.</span><span class="sxs-lookup"><span data-stu-id="1fa14-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="1fa14-108">Se l' **Archivio di file aggiuntivo di Office 365** non è presente nell'elenco dei componenti aggiuntivi disponibili, significa che il piano non è idoneo.</span><span class="sxs-lookup"><span data-stu-id="1fa14-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="1fa14-109">Per ulteriori informazioni, vedere [è il mio piano idoneo?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="1fa14-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="1fa14-110">Se l'abbonamento è stato acquistato tramite contratti multilicenza o CSP, non è possibile acquistare **Office 365 extra file storage** for Your Organization direttamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fa14-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="1fa14-111">Contattare il rappresentante o il partner per assistenza.</span><span class="sxs-lookup"><span data-stu-id="1fa14-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1fa14-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1fa14-112">Before you begin</span></span>

<span data-ttu-id="1fa14-113">Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore globale o di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1fa14-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="1fa14-114">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1fa14-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="1fa14-115">Visualizzazione dello spazio di archiviazione disponibile</span><span class="sxs-lookup"><span data-stu-id="1fa14-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1fa14-116">Nell'interfaccia di amministrazione di SharePoint, andare alla pagina <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">siti attivi</a> e accedere con un account che disponga [delle autorizzazioni di amministratore](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1fa14-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="1fa14-117">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione utilizzata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1fa14-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="1fa14-118">Se nell'organizzazione è stata configurata la multi-Geo in Office 365, la barra Visualizza anche la quantità di spazio di archiviazione utilizzata in tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="1fa14-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra di archiviazione nella pagina siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="1fa14-120">Lo spazio di archiviazione utilizzato non include le modifiche apportate nelle ultime 24-48 ore.</span><span class="sxs-lookup"><span data-stu-id="1fa14-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1fa14-121">Accedere https://portal.office.de come amministratore globale o di SharePoint e quindi selezionare il riquadro amministratore per aprire l'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1fa14-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="1fa14-122">Se viene visualizzato un messaggio che non dispone dell'autorizzazione per accedere alla pagina, significa che non si dispone delle autorizzazioni di amministratore Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1fa14-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="1fa14-123">Nel riquadro sinistro, in interfaccia di **Amministrazione**, selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="1fa14-124">Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1fa14-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="1fa14-125">Nel riquadro a sinistra dell'interfaccia di amministrazione di SharePoint selezionare **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="1fa14-126">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione utilizzata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1fa14-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Barra di archiviazione nella pagina siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="1fa14-128">Lo spazio di archiviazione utilizzato non include le modifiche apportate nelle ultime 24-48 ore.</span><span class="sxs-lookup"><span data-stu-id="1fa14-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1fa14-129">Accedere https://login.partner.microsoftonline.cn/ come amministratore globale o di SharePoint e quindi selezionare il riquadro amministratore per aprire l'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1fa14-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="1fa14-130">Se viene visualizzato un messaggio che non dispone dell'autorizzazione per accedere alla pagina, significa che non si dispone delle autorizzazioni di amministratore Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1fa14-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="1fa14-131">Nel riquadro sinistro, in interfaccia di **Amministrazione**, selezionare **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="1fa14-132">Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1fa14-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="1fa14-133">Nel riquadro a sinistra dell'interfaccia di amministrazione di SharePoint selezionare **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="1fa14-134">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione utilizzata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1fa14-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Barra di archiviazione nella pagina siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="1fa14-136">Lo spazio di archiviazione utilizzato non include le modifiche apportate nelle ultime 24-48 ore.</span><span class="sxs-lookup"><span data-stu-id="1fa14-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="1fa14-137">Dopo aver identificato la quantità di spazio di archiviazione in uso, è possibile aggiungerne altro o rimuoverlo dall'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1fa14-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="1fa14-138">Per sapere quanto costerà aggiungere spazio di archiviazione, seguire i passaggi descritti in questo articolo ed esaminare le informazioni sui prezzi prima di acquistare.</span><span class="sxs-lookup"><span data-stu-id="1fa14-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="1fa14-139">Per informazioni sull'impostazione dei limiti di archiviazione delle raccolte siti, vedere [gestire i limiti di archiviazione delle raccolte siti](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="1fa14-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="1fa14-140">Aggiungere spazio di archiviazione all'abbonamento</span><span class="sxs-lookup"><span data-stu-id="1fa14-140">Add storage to your subscription</span></span>

<span data-ttu-id="1fa14-141">Se non è stato ancora acquistato un ulteriore spazio di archiviazione per l'abbonamento, è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="1fa14-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1fa14-142">Nell'interfaccia di amministrazione, andare alla **Billing** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servizi di acquisto</a> per la fatturazione.</span><span class="sxs-lookup"><span data-stu-id="1fa14-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="1fa14-143">Nella parte inferiore della pagina **acquisto servizi** selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1fa14-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="1fa14-144">Selezionare **Office 365 extra file storage**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="1fa14-145">Nella pagina **Office 365 extra file storage** , se visualizzata, scegliere la sottoscrizione di base e quindi immettere il numero di gigabyte di spazio di archiviazione che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1fa14-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="1fa14-146">Selezionare **Estrai ora**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="1fa14-147">In **questa** pagina, verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="1fa14-148">Nella pagina **ordine completo** verificare il totale.</span><span class="sxs-lookup"><span data-stu-id="1fa14-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="1fa14-149">Se è necessario apportare modifiche, selezionare **modifica ordine**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="1fa14-150">Se l'ordine richiede una verifica del credito, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="1fa14-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="1fa14-151">Al termine, selezionare **Ordina per** \> **accedere a Home page di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1fa14-152">Nell'interfaccia di amministrazione, andare alla pagina **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">abbonamenti</a> di fatturazione.  </span><span class="sxs-lookup"><span data-stu-id="1fa14-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="1fa14-153">Nella pagina **abbonamenti** scegliere la sottoscrizione a cui si desidera aggiungere spazio di archiviazione, quindi selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1fa14-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="1fa14-155">Se i **componenti aggiuntivi**non sono visibili e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="1fa14-156">Selezionare **acquista componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1fa14-156">Select **Buy add-ons**.</span></span>

    ![Acquistare un collegamento per i componenti aggiuntivi nella pagina abbonamenti dell'interfaccia di amministrazione.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="1fa14-158">Nella pagina **acquisto servizi** , passare il mouse o toccare **Office 365 extra file storage**, quindi scegliere **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="1fa14-159">Immettere il numero di licenze utente necessarie e, se visualizzato, scegliere una sottoscrizione di base.</span><span class="sxs-lookup"><span data-stu-id="1fa14-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="1fa14-160">Selezionare **Estrai ora**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="1fa14-161">In **questa** pagina, verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="1fa14-162">Nella pagina **ordine completo** selezionare **luogo ordine**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1fa14-163">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="1fa14-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="1fa14-164">Nella pagina **abbonamenti** scegliere la sottoscrizione a cui si desidera aggiungere spazio di archiviazione, quindi selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1fa14-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="1fa14-166">Se i **componenti aggiuntivi**non sono visibili e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="1fa14-167">Selezionare **acquista componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1fa14-167">Select **Buy add-ons**.</span></span>

    ![Acquistare un collegamento per i componenti aggiuntivi nella pagina abbonamenti dell'interfaccia di amministrazione.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="1fa14-169">Nella pagina **acquisto servizi** , passare il mouse o toccare **Office 365 extra file storage**, quindi scegliere **Acquista ora**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="1fa14-170">Immettere il numero di licenze utente necessarie e, se visualizzato, scegliere una sottoscrizione di base.</span><span class="sxs-lookup"><span data-stu-id="1fa14-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="1fa14-171">Selezionare **Estrai ora**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="1fa14-172">In **questa** pagina, verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="1fa14-173">Nella pagina **ordine completo** selezionare **luogo ordine**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="1fa14-174">Aumentare o diminuire lo spazio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="1fa14-174">Increase or decrease storage</span></span>

<span data-ttu-id="1fa14-175">Se si è già acquistato un file di archiviazione supplementare tramite il componente aggiuntivo di **archiviazione file aggiuntivo di Office 365** , è possibile utilizzare questi passaggi per aumentare o diminuire lo spazio di archiviazione aggiuntivo per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1fa14-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="1fa14-176">È possibile ridurre lo spazio di archiviazione a un minimo di 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="1fa14-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="1fa14-177">Per rimuovere tutto lo spazio di archiviazione aggiuntivo, [contattare il supporto](../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="1fa14-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1fa14-178">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="1fa14-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="1fa14-179">Nella scheda **prodotti** selezionare la sottoscrizione contenente il componente aggiuntivo di **archiviazione file aggiuntivo di Office 365** .</span><span class="sxs-lookup"><span data-stu-id="1fa14-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="1fa14-180">Nella sezione **componenti** aggiuntivi della pagina Dettagli prodotto selezionare **Gestisci componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1fa14-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="1fa14-181">Nel riquadro **Gestisci componenti** aggiuntivi, nell'elenco **componente aggiuntivo** , scegliere **Office 365 extra file storage**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="1fa14-182">Nella casella di testo **quantità** immettere il numero di GB di spazio di archiviazione desiderato per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="1fa14-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="1fa14-183">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1fa14-184">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="1fa14-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="1fa14-185">Nella pagina **abbonamenti** selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1fa14-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="1fa14-187">Se i **componenti aggiuntivi**non sono visibili e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="1fa14-188">In **Office 365 extra file storage**selezionare **Change Quantity**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Collegamento Cambio di quantità.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="1fa14-190">Nel riquadro a destra, immettere il numero totale di Gigabyte necessari, quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="1fa14-191">Ad esempio, se attualmente si hanno 200 gigabyte di spazio di archiviazione file aggiuntivo ma ne servono solo 100, immettere **100** nella casella.</span><span class="sxs-lookup"><span data-stu-id="1fa14-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="1fa14-192">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1fa14-193">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="1fa14-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="1fa14-194">Nella pagina **abbonamenti** selezionare **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1fa14-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="1fa14-196">Se i **componenti aggiuntivi**non sono visibili e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="1fa14-197">In **Office 365 extra file storage**selezionare **Change Quantity**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Collegamento Cambio di quantità.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="1fa14-199">Nel riquadro a destra, immettere il numero totale di Gigabyte necessari, quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="1fa14-200">Ad esempio, se attualmente si hanno 200 gigabyte di spazio di archiviazione file aggiuntivo ma ne servono solo 100, immettere **100** nella casella.</span><span class="sxs-lookup"><span data-stu-id="1fa14-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="1fa14-201">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="1fa14-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="1fa14-202">Quali piani sono idonei per Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="1fa14-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="1fa14-203">Office 365 Extra File Storage è disponibile per gli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fa14-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="1fa14-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="1fa14-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="1fa14-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="1fa14-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="1fa14-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="1fa14-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="1fa14-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="1fa14-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="1fa14-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="1fa14-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="1fa14-209">Office per il Web con SharePoint piano 1</span><span class="sxs-lookup"><span data-stu-id="1fa14-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="1fa14-210">Office per il Web con SharePoint piano 2</span><span class="sxs-lookup"><span data-stu-id="1fa14-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="1fa14-211">SharePoint Online Piano 1</span><span class="sxs-lookup"><span data-stu-id="1fa14-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="1fa14-212">SharePoint Online Piano 2</span><span class="sxs-lookup"><span data-stu-id="1fa14-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="1fa14-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="1fa14-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="1fa14-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="1fa14-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="1fa14-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1fa14-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="1fa14-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="1fa14-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="1fa14-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1fa14-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="1fa14-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="1fa14-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="1fa14-219">Office 365 è disponibile anche per i piani GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="1fa14-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="1fa14-220">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="1fa14-220">Related content</span></span>

<span data-ttu-id="1fa14-221">[Gestire i limiti di spazio di archiviazione del sito](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (articolo) </span><span class="sxs-lookup"><span data-stu-id="1fa14-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="1fa14-222">[Impostare lo spazio di archiviazione predefinito per gli utenti di OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(articolo)</span><span class="sxs-lookup"><span data-stu-id="1fa14-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
