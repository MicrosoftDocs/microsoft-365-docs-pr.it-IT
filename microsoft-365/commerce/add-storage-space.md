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
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Informazioni su come aggiungere e ridurre l'archiviazione dei file nell'abbonamento a Microsoft 365. Con spazio di archiviazione file aggiuntivo, è possibile archiviare più contenuto in SharePoint Online e OneDrive.
ms.date: ''
ms.openlocfilehash: 626cc81faea43ebdcf618a4f26c33069bae6a206
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405889"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="1a93b-104">Aggiungere spazio di archiviazione per l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="1a93b-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1a93b-105">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="1a93b-105">The admin center is changing.</span></span> <span data-ttu-id="1a93b-106">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="1a93b-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="1a93b-107">Se lo spazio di archiviazione per le raccolte di siti di SharePoint Online sta per esaurirsi, è possibile aggiungere altro spazio all'abbonamento, se il piano è idoneo.</span><span class="sxs-lookup"><span data-stu-id="1a93b-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="1a93b-108">Se office **365 Extra File Storage** non è presente nell'elenco dei componenti aggiuntivi disponibili, significa che il piano non è idoneo.</span><span class="sxs-lookup"><span data-stu-id="1a93b-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="1a93b-109">Per altre informazioni, vedere [Il piano è idoneo?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="1a93b-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="1a93b-110">Se l'abbonamento è stato acquistato tramite contratti multilicenza o un provider di servizi di configurazione, non è possibile acquistare Spazio di archiviazione file aggiuntivo di **Office 365** per l'organizzazione direttamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a93b-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="1a93b-111">Contattare il rappresentante o il partner per assistenza.</span><span class="sxs-lookup"><span data-stu-id="1a93b-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1a93b-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1a93b-112">Before you begin</span></span>

<span data-ttu-id="1a93b-113">Per eseguire le attività di questo articolo, è necessario essere un amministratore globale o di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1a93b-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="1a93b-114">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1a93b-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="1a93b-115">Visualizzare lo spazio di archiviazione disponibile</span><span class="sxs-lookup"><span data-stu-id="1a93b-115">View available storage</span></span>

1. <span data-ttu-id="1a93b-116">Nell'interfaccia di amministrazione di SharePoint passare alla pagina <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Siti</a> attivi e accedere con un account che dispone delle autorizzazioni di amministratore [per](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1a93b-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="1a93b-117">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione usata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1a93b-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="1a93b-118">Se l'organizzazione ha configurato Multi-Geo in Office 365, la barra mostra anche la quantità di spazio di archiviazione usato in tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="1a93b-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra di archiviazione nella pagina Siti attivi](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="1a93b-120">Lo spazio di archiviazione usato non include le modifiche apportate nelle ultime 24 - 48 ore.</span><span class="sxs-lookup"><span data-stu-id="1a93b-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="1a93b-121">Dopo aver determinato la quantità di spazio di archiviazione in uso, è possibile aggiungere o rimuovere lo spazio di archiviazione per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1a93b-121">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="1a93b-122">Per scoprire quanto costerà aggiungere spazio di archiviazione, segui i passaggi descritti in questo articolo ed esamina le informazioni sui prezzi prima di acquistarne altre.</span><span class="sxs-lookup"><span data-stu-id="1a93b-122">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="1a93b-123">Per informazioni sull'impostazione dei limiti di archiviazione per le raccolte siti, vedere [Gestire i limiti di archiviazione delle raccolte siti.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="1a93b-123">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="1a93b-124">Aggiungere spazio di archiviazione all'abbonamento</span><span class="sxs-lookup"><span data-stu-id="1a93b-124">Add storage to your subscription</span></span>

<span data-ttu-id="1a93b-125">Se non si è ancora acquistato spazio di archiviazione aggiuntivo per l'abbonamento, è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="1a93b-125">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="1a93b-126">Nell'interfaccia di amministrazione passare alla pagina **Servizi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">di acquisto della</a> fatturazione.</span><span class="sxs-lookup"><span data-stu-id="1a93b-126">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="1a93b-127">Nella parte inferiore della **pagina** Acquisto  di servizi, nella sezione Componenti aggiuntivi, trovare Spazio di archiviazione file aggiuntivo di **Office 365** e selezionare **Dettagli.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-127">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="1a93b-128">Nella pagina dei dettagli del prodotto selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-128">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="1a93b-129">Se necessario, scegliere la sottoscrizione di base, quindi immettere il numero di gigabyte di archiviazione che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1a93b-129">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="1a93b-130">Selezionare **Estrai ora.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-130">Select **Check out now**.</span></span>
6. <span data-ttu-id="1a93b-131">Nella pagina **Come funziona?** verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-131">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="1a93b-132">Nella pagina **Completa ordine** verificare il totale.</span><span class="sxs-lookup"><span data-stu-id="1a93b-132">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="1a93b-133">Se è necessario apportare modifiche, selezionare **Modifica ordine.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-133">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="1a93b-134">Se l'ordine richiede una verifica del credito, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="1a93b-134">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="1a93b-135">Al termine, selezionare Place **order** \> **Go to Admin Home.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-135">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="1a93b-136">Aumentare o diminuire lo spazio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="1a93b-136">Increase or decrease storage</span></span>

<span data-ttu-id="1a93b-137">Se è già stato acquistato spazio di archiviazione aggiuntivo per i file tramite il componente aggiuntivo Office **365 Extra File Storage,** è possibile usare questa procedura per aumentare o ridurre lo spazio di archiviazione aggiuntivo per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="1a93b-137">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="1a93b-138">È possibile ridurre lo spazio di archiviazione fino a 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="1a93b-138">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="1a93b-139">Per rimuovere tutto lo spazio di archiviazione aggiuntivo, [contattare il supporto](../admin/contact-support-for-business-products.md)tecnico.</span><span class="sxs-lookup"><span data-stu-id="1a93b-139">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="1a93b-140">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="1a93b-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="1a93b-141">Nella scheda **Prodotti** selezionare l'abbonamento contenente il componente aggiuntivo Di archiviazione file aggiuntivo di **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-141">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="1a93b-142">Nella sezione Componenti aggiuntivi  della pagina dei dettagli del prodotto selezionare **Gestisci componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-142">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="1a93b-143">**Nell'elenco Componenti** aggiuntivi del riquadro  Gestisci componenti aggiuntivi scegliere Spazio di archiviazione file aggiuntivo di **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="1a93b-143">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="1a93b-144">Nella casella **di** testo Quantità immettere il numero di GB di spazio di archiviazione desiderato per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="1a93b-144">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="1a93b-145">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1a93b-145">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="1a93b-146">Quali piani sono idonei per Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="1a93b-146">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="1a93b-147">Office 365 Extra File Storage è disponibile per gli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a93b-147">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="1a93b-148">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="1a93b-148">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="1a93b-149">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="1a93b-149">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="1a93b-150">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="1a93b-150">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="1a93b-151">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="1a93b-151">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="1a93b-152">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="1a93b-152">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="1a93b-153">Office per il Web con SharePoint Piano 1</span><span class="sxs-lookup"><span data-stu-id="1a93b-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="1a93b-154">Office per il Web con SharePoint Piano 2</span><span class="sxs-lookup"><span data-stu-id="1a93b-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="1a93b-155">SharePoint Online Piano 1</span><span class="sxs-lookup"><span data-stu-id="1a93b-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="1a93b-156">SharePoint Online Piano 2</span><span class="sxs-lookup"><span data-stu-id="1a93b-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="1a93b-157">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="1a93b-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="1a93b-158">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="1a93b-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="1a93b-159">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1a93b-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="1a93b-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="1a93b-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="1a93b-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1a93b-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="1a93b-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="1a93b-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="1a93b-163">Office 365 Extra File Storage è disponibile anche per i piani GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="1a93b-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="1a93b-164">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="1a93b-164">Related content</span></span>

<span data-ttu-id="1a93b-165">[Gestire i limiti di archiviazione del sito](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (articolo)</span><span class="sxs-lookup"><span data-stu-id="1a93b-165">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="1a93b-166">[Impostare lo spazio di archiviazione predefinito per gli utenti di OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(articolo)</span><span class="sxs-lookup"><span data-stu-id="1a93b-166">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>