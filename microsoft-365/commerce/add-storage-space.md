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
description: Informazioni su come aggiungere e ridurre l'archiviazione dei file nell'abbonamento a Microsoft 365. Con spazio di archiviazione file aggiuntivo, è possibile archiviare più contenuto in SharePoint Online e OneDrive.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114908"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="a7a66-104">Aggiungere spazio di archiviazione per l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="a7a66-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a7a66-105">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="a7a66-105">The admin center is changing.</span></span> <span data-ttu-id="a7a66-106">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="a7a66-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="a7a66-107">Se lo spazio di archiviazione per le raccolte di siti di SharePoint Online sta per esaurirsi, è possibile aggiungere altro spazio all'abbonamento, se il piano è idoneo.</span><span class="sxs-lookup"><span data-stu-id="a7a66-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="a7a66-108">Se office **365 Extra File Storage** non è presente nell'elenco dei componenti aggiuntivi disponibili, significa che il piano non è idoneo.</span><span class="sxs-lookup"><span data-stu-id="a7a66-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="a7a66-109">Per altre informazioni, vedere [Il piano è idoneo?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="a7a66-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="a7a66-110">Se l'abbonamento è stato acquistato tramite contratti multilicenza o un provider di servizi di configurazione, non è possibile acquistare Spazio di archiviazione file aggiuntivo di **Office 365** per l'organizzazione direttamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7a66-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="a7a66-111">Contattare il proprio rappresentante o partner per assistenza.</span><span class="sxs-lookup"><span data-stu-id="a7a66-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a7a66-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a7a66-112">Before you begin</span></span>

<span data-ttu-id="a7a66-113">Per eseguire le attività di questo articolo, è necessario essere un amministratore globale o di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a7a66-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="a7a66-114">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a7a66-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="a7a66-115">Visualizzare lo spazio di archiviazione disponibile</span><span class="sxs-lookup"><span data-stu-id="a7a66-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a7a66-116">Nell'interfaccia di amministrazione di SharePoint passare alla pagina <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Siti</a> attivi e accedere con un account che dispone delle autorizzazioni di amministratore [per](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a7a66-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="a7a66-117">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione usata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="a7a66-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="a7a66-118">Se l'organizzazione ha configurato Multi-Geo in Office 365, la barra mostra anche la quantità di spazio di archiviazione usato in tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="a7a66-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra di archiviazione nella pagina Siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="a7a66-120">Lo spazio di archiviazione usato non include le modifiche apportate nelle ultime 24 - 48 ore.</span><span class="sxs-lookup"><span data-stu-id="a7a66-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a7a66-121">Accedere come amministratore globale o di SharePoint e quindi selezionare il riquadro https://portal.office.de Amministrazione per aprire l'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="a7a66-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="a7a66-122">Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere alla pagina, significa che non si dispone delle autorizzazioni di amministratore di Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a7a66-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="a7a66-123">Nel riquadro sinistro, in **Interfaccia di amministrazione,** selezionare **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="a7a66-124">Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a7a66-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="a7a66-125">Nel riquadro a sinistra dell'interfaccia di amministrazione di SharePoint selezionare **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="a7a66-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="a7a66-126">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione usata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="a7a66-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Barra di archiviazione nella pagina Siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="a7a66-128">Lo spazio di archiviazione usato non include le modifiche apportate nelle ultime 24 - 48 ore.</span><span class="sxs-lookup"><span data-stu-id="a7a66-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a7a66-129">Accedere come amministratore globale o di SharePoint e quindi selezionare il riquadro https://login.partner.microsoftonline.cn/ Amministrazione per aprire l'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="a7a66-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="a7a66-130">Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere alla pagina, significa che non si dispone delle autorizzazioni di amministratore di Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a7a66-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="a7a66-131">Nel riquadro sinistro, in **Interfaccia di amministrazione,** selezionare **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="a7a66-132">Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a7a66-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="a7a66-133">Nel riquadro a sinistra dell'interfaccia di amministrazione di SharePoint selezionare **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="a7a66-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="a7a66-134">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione usata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="a7a66-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Barra di archiviazione nella pagina Siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="a7a66-136">Lo spazio di archiviazione usato non include le modifiche apportate nelle ultime 24 - 48 ore.</span><span class="sxs-lookup"><span data-stu-id="a7a66-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="a7a66-137">Dopo aver identificato la quantità di spazio di archiviazione in uso, è possibile aggiungerne altro o rimuoverlo dall'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="a7a66-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="a7a66-138">Per scoprire quanto costerà aggiungere spazio di archiviazione, segui i passaggi descritti in questo articolo ed esamina le informazioni sui prezzi prima dell'acquisto.</span><span class="sxs-lookup"><span data-stu-id="a7a66-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="a7a66-139">Per informazioni sull'impostazione dei limiti di archiviazione per le raccolte siti, vedere [Gestire i limiti di archiviazione delle raccolte siti.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="a7a66-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="a7a66-140">Aggiungere spazio di archiviazione all'abbonamento</span><span class="sxs-lookup"><span data-stu-id="a7a66-140">Add storage to your subscription</span></span>

<span data-ttu-id="a7a66-141">Se non è stato ancora acquistato spazio di archiviazione aggiuntivo per l'abbonamento, è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="a7a66-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a7a66-142">Nell'interfaccia di amministrazione passare alla pagina **Servizi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">di acquisto della</a> fatturazione.</span><span class="sxs-lookup"><span data-stu-id="a7a66-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="a7a66-143">Nella parte inferiore della **pagina Acquisto di** servizi selezionare Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="a7a66-144">Selezionare Spazio di archiviazione file aggiuntivo di **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="a7a66-145">Nella pagina Spazio di archiviazione file aggiuntivo di **Office 365,** se visualizzata, scegliere l'abbonamento di base, quindi immettere il numero di gigabyte di archiviazione che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="a7a66-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="a7a66-146">Selezionare **Estrai ora.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="a7a66-147">Nella pagina **Come funziona?** verificare il numero di gigabyte di archiviazione selezionati, esaminare le informazioni sui prezzi e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="a7a66-148">Nella pagina **Completa ordine** verificare il totale.</span><span class="sxs-lookup"><span data-stu-id="a7a66-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="a7a66-149">Se è necessario apportare modifiche, selezionare **Modifica ordine.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="a7a66-150">Se l'ordine richiede una verifica del credito, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a7a66-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="a7a66-151">Al termine, selezionare Place **order** \> **Go to Admin Home.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a7a66-152">Nell'interfaccia di amministrazione passare alla pagina **Sottoscrizioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">fatturazione.</a>  </span><span class="sxs-lookup"><span data-stu-id="a7a66-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="a7a66-153">Nella pagina **Sottoscrizioni** scegliere l'abbonamento a cui si desidera aggiungere spazio di archiviazione, quindi selezionare **Componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="a7a66-155">Se i componenti aggiuntivi non sono visualizzati e l'abbonamento è stato acquistato tramite un partner, selezionare **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="a7a66-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="a7a66-156">Seleziona **Acquista componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-156">Select **Buy add-ons**.</span></span>

    ![Collegamento Acquista componenti aggiuntivi nella pagina Abbonamenti dell'interfaccia di amministrazione.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="a7a66-158">Nella pagina **Acquisto di servizi,** posizionare il puntatore del mouse o toccare Archiviazione file extra di **Office 365,** quindi selezionare **Acquista ora.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="a7a66-159">Immettere il numero di licenze utente necessarie e, se visualizzato, scegliere un abbonamento di base.</span><span class="sxs-lookup"><span data-stu-id="a7a66-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="a7a66-160">Selezionare **Estrai ora.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="a7a66-161">Nella pagina **Come funziona?** verificare il numero di gigabyte di archiviazione selezionati, esaminare le informazioni sui prezzi e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="a7a66-162">Nella pagina **Completa ordine** selezionare **Effettuare l'ordine.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a7a66-163">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="a7a66-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="a7a66-164">Nella pagina **Sottoscrizioni** scegliere la sottoscrizione a cui si desidera aggiungere spazio di archiviazione, quindi selezionare **Componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="a7a66-166">Se i componenti aggiuntivi non sono **visualizzati** e l'abbonamento è stato acquistato tramite un partner, selezionare Volume Licensing Service **Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="a7a66-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="a7a66-167">Seleziona **Acquista componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-167">Select **Buy add-ons**.</span></span>

    ![Collegamento Acquista componenti aggiuntivi nella pagina Abbonamenti dell'interfaccia di amministrazione.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="a7a66-169">Nella pagina **Acquisto di servizi,** posizionare il puntatore del mouse o toccare Archiviazione file extra di **Office 365,** quindi selezionare **Acquista ora.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="a7a66-170">Immettere il numero di licenze utente necessarie e, se visualizzato, scegliere un abbonamento di base.</span><span class="sxs-lookup"><span data-stu-id="a7a66-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="a7a66-171">Selezionare **Estrai ora.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="a7a66-172">Nella pagina **Come funziona?** verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="a7a66-173">Nella pagina **Completa ordine** selezionare **Effettuare l'ordine.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="a7a66-174">Aumentare o diminuire lo spazio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a7a66-174">Increase or decrease storage</span></span>

<span data-ttu-id="a7a66-175">Se è già stato acquistato spazio di archiviazione aggiuntivo per i file tramite il componente aggiuntivo Office **365 Extra File Storage,** è possibile usare questa procedura per aumentare o ridurre lo spazio di archiviazione aggiuntivo per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="a7a66-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="a7a66-176">È possibile ridurre lo spazio di archiviazione fino a 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="a7a66-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="a7a66-177">Per rimuovere tutto lo spazio di archiviazione aggiuntivo, [contattare il supporto](../admin/contact-support-for-business-products.md)tecnico.</span><span class="sxs-lookup"><span data-stu-id="a7a66-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a7a66-178">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="a7a66-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="a7a66-179">Nella scheda **Prodotti** selezionare l'abbonamento contenente il componente aggiuntivo Di archiviazione file aggiuntivo di **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="a7a66-180">Nella sezione Componenti aggiuntivi  della pagina dei dettagli del prodotto selezionare **Gestisci componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="a7a66-181">**Nell'elenco Componenti** aggiuntivi del riquadro  Gestisci componenti aggiuntivi scegliere Spazio di archiviazione file aggiuntivo di **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="a7a66-182">Nella casella **di** testo Quantità immettere il numero di GB di spazio di archiviazione desiderato per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="a7a66-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="a7a66-183">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a7a66-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a7a66-184">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="a7a66-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="a7a66-185">Nella pagina **Abbonamenti** selezionare **Componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="a7a66-187">Se i componenti aggiuntivi non sono **visualizzati** e l'abbonamento è stato acquistato tramite un partner, selezionare Volume Licensing Service **Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="a7a66-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="a7a66-188">In Spazio di archiviazione file aggiuntivo di **Office 365** selezionare **Cambia quantità.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Collegamento Cambio di quantità.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="a7a66-190">Nel riquadro destro immettere il numero totale di gigabyte necessari, quindi selezionare **Invia.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="a7a66-191">Ad esempio, se attualmente si hanno 200 gigabyte di spazio di archiviazione file aggiuntivo ma ne servono solo 100, immettere **100** nella casella.</span><span class="sxs-lookup"><span data-stu-id="a7a66-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="a7a66-192">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7a66-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a7a66-193">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="a7a66-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="a7a66-194">Nella pagina **Abbonamenti** selezionare **Componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="a7a66-196">Se i componenti aggiuntivi non sono **visualizzati** e l'abbonamento è stato acquistato tramite un partner, selezionare Volume Licensing Service **Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="a7a66-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="a7a66-197">In Spazio di archiviazione file aggiuntivo di **Office 365** selezionare **Cambia quantità.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Collegamento Cambio di quantità.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="a7a66-199">Nel riquadro destro immettere il numero totale di gigabyte necessari, quindi selezionare **Invia.**</span><span class="sxs-lookup"><span data-stu-id="a7a66-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="a7a66-200">Ad esempio, se attualmente si hanno 200 gigabyte di spazio di archiviazione file aggiuntivo ma ne servono solo 100, immettere **100** nella casella.</span><span class="sxs-lookup"><span data-stu-id="a7a66-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="a7a66-201">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7a66-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="a7a66-202">Quali piani sono idonei per Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="a7a66-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="a7a66-203">Office 365 Extra File Storage è disponibile per gli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7a66-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="a7a66-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="a7a66-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="a7a66-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="a7a66-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="a7a66-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="a7a66-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="a7a66-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="a7a66-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="a7a66-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="a7a66-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="a7a66-209">Office per il Web con SharePoint Piano 1</span><span class="sxs-lookup"><span data-stu-id="a7a66-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="a7a66-210">Office per il Web con SharePoint Piano 2</span><span class="sxs-lookup"><span data-stu-id="a7a66-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="a7a66-211">SharePoint Online Piano 1</span><span class="sxs-lookup"><span data-stu-id="a7a66-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="a7a66-212">SharePoint Online Piano 2</span><span class="sxs-lookup"><span data-stu-id="a7a66-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="a7a66-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="a7a66-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="a7a66-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="a7a66-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="a7a66-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="a7a66-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="a7a66-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="a7a66-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="a7a66-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a7a66-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="a7a66-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="a7a66-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="a7a66-219">Office 365 Extra File Storage è disponibile anche per i piani GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="a7a66-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="a7a66-220">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="a7a66-220">Related content</span></span>

<span data-ttu-id="a7a66-221">[Gestire i limiti di archiviazione del](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) sito (articolo)</span><span class="sxs-lookup"><span data-stu-id="a7a66-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="a7a66-222">[Impostare lo spazio di archiviazione predefinito per gli utenti di OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(articolo)</span><span class="sxs-lookup"><span data-stu-id="a7a66-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
