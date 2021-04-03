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
description: Informazioni su come aggiungere e ridurre l'archiviazione di file nell'abbonamento a Microsoft 365. Con spazio di archiviazione file aggiuntivo, è possibile archiviare più contenuto in SharePoint Online e OneDrive.
ms.date: ''
ms.openlocfilehash: d65677b9c078026343410b53acd48932258cb4b1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576962"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="9254a-104">Aggiungere spazio di archiviazione per l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="9254a-104">Add storage space for your subscription</span></span>

<span data-ttu-id="9254a-105">Se lo spazio di archiviazione per le raccolte di siti di SharePoint Online sta per esaurirsi, è possibile aggiungere altro spazio all'abbonamento, se il piano è idoneo.</span><span class="sxs-lookup"><span data-stu-id="9254a-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="9254a-106">Se l'archivio file aggiuntivo di **Office 365** non è presente nell'elenco dei componenti aggiuntivi disponibili, significa che il piano non è idoneo.</span><span class="sxs-lookup"><span data-stu-id="9254a-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="9254a-107">Per ulteriori informazioni, vedere [Il piano è idoneo?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="9254a-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="9254a-108">Se l'abbonamento è stato acquistato tramite contratti multilicenza o un CSP, non è possibile acquistare **Office 365 Extra File Storage** per l'organizzazione direttamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9254a-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="9254a-109">Per assistenza, contattare il proprio rappresentante o partner.</span><span class="sxs-lookup"><span data-stu-id="9254a-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9254a-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9254a-110">Before you begin</span></span>

<span data-ttu-id="9254a-111">Per eseguire le attività in questo articolo, è necessario essere un amministratore globale o di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9254a-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="9254a-112">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9254a-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="9254a-113">Visualizzare lo spazio di archiviazione disponibile</span><span class="sxs-lookup"><span data-stu-id="9254a-113">View available storage</span></span>

1. <span data-ttu-id="9254a-114">Nell'interfaccia di amministrazione di SharePoint passare alla pagina <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Siti</a> attivi e accedere con un account con autorizzazioni [di](/sharepoint/sharepoint-admin-role) amministratore per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9254a-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="9254a-115">Nell'angolo in alto a destra della pagina, vedere la quantità di spazio di archiviazione usata in tutti i siti e lo spazio di archiviazione totale per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="9254a-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="9254a-116">Se l'organizzazione ha configurato Multi-Geo in Office 365, la barra mostra anche la quantità di spazio di archiviazione usato in tutte le posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="9254a-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra di archiviazione nella pagina Siti attivi](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="9254a-118">Lo spazio di archiviazione usato non include le modifiche apportate nelle ultime 24 - 48 ore.</span><span class="sxs-lookup"><span data-stu-id="9254a-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="9254a-119">Dopo aver determinato la quantità di spazio di archiviazione in uso, è possibile aggiungere o rimuovere spazio di archiviazione per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="9254a-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="9254a-120">Per scoprire quanto costerà aggiungere spazio di archiviazione, seguire la procedura descritta in questo articolo ed esaminare le informazioni sui prezzi prima di acquistarne altre.</span><span class="sxs-lookup"><span data-stu-id="9254a-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="9254a-121">Per informazioni sull'impostazione dei limiti di archiviazione per le raccolte [siti,](/sharepoint/manage-site-collection-storage-limits)vedere Manage site collection storage limits .</span><span class="sxs-lookup"><span data-stu-id="9254a-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="9254a-122">Aggiungere spazio di archiviazione all'abbonamento</span><span class="sxs-lookup"><span data-stu-id="9254a-122">Add storage to your subscription</span></span>

<span data-ttu-id="9254a-123">Se non hai ancora acquistato spazio di archiviazione aggiuntivo per l'abbonamento, puoi farlo.</span><span class="sxs-lookup"><span data-stu-id="9254a-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="9254a-124">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Acquisto servizi.</a></span><span class="sxs-lookup"><span data-stu-id="9254a-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="9254a-125">Nella parte inferiore della pagina **Acquista** servizi, nella sezione Componenti aggiuntivi, individuare Archiviazione file extra **di Office 365** e selezionare **Dettagli.** </span><span class="sxs-lookup"><span data-stu-id="9254a-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="9254a-126">Nella pagina dei dettagli del prodotto selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9254a-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="9254a-127">Se necessario, scegliere la sottoscrizione di base, quindi immettere il numero di gigabyte di spazio di archiviazione che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="9254a-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="9254a-128">Selezionare **Estrai ora.**</span><span class="sxs-lookup"><span data-stu-id="9254a-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="9254a-129">Nella pagina **Come funziona?** verificare il numero di gigabyte di spazio di archiviazione selezionato, esaminare le informazioni sui prezzi e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="9254a-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="9254a-130">Nella pagina **Completa ordine** verificare il totale.</span><span class="sxs-lookup"><span data-stu-id="9254a-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="9254a-131">Se è necessario apportare modifiche, selezionare **Modifica ordine.**</span><span class="sxs-lookup"><span data-stu-id="9254a-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="9254a-132">Se l'ordine richiede una verifica del credito, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="9254a-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="9254a-133">Al termine, selezionare Place **order** \> **Go to Admin Home.**</span><span class="sxs-lookup"><span data-stu-id="9254a-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="9254a-134">Aumentare o diminuire lo spazio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="9254a-134">Increase or decrease storage</span></span>

<span data-ttu-id="9254a-135">Se è già stato acquistato spazio di archiviazione file aggiuntivo tramite il componente aggiuntivo Di archiviazione file extra di **Office 365,** è possibile utilizzare questa procedura per aumentare o ridurre lo spazio di archiviazione aggiuntivo per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="9254a-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="9254a-136">È possibile ridurre lo spazio di archiviazione fino a 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="9254a-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="9254a-137">Per rimuovere tutto lo spazio di archiviazione aggiuntivo, [contattare il supporto](../admin/contact-support-for-business-products.md)tecnico .</span><span class="sxs-lookup"><span data-stu-id="9254a-137">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="9254a-138">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="9254a-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="9254a-139">Nella scheda **Prodotti** selezionare l'abbonamento che contiene il componente aggiuntivo Di archiviazione file extra di **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="9254a-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="9254a-140">Nella sezione Componenti aggiuntivi  della pagina dei dettagli del prodotto selezionare **Gestisci componenti aggiuntivi**.</span><span class="sxs-lookup"><span data-stu-id="9254a-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="9254a-141">**Nell'elenco Componenti aggiuntivi del** riquadro  Gestisci componenti aggiuntivi scegliere Archiviazione file extra di **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="9254a-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="9254a-142">Nella casella **di** testo Quantità immettere il numero di GBs di spazio di archiviazione desiderato per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9254a-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="9254a-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9254a-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="9254a-144">Quali piani sono idonei per Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="9254a-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="9254a-145">Office 365 Extra File Storage è disponibile per gli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9254a-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="9254a-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="9254a-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="9254a-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="9254a-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="9254a-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="9254a-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="9254a-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="9254a-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="9254a-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="9254a-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="9254a-151">Office per il Web con SharePoint Piano 1</span><span class="sxs-lookup"><span data-stu-id="9254a-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="9254a-152">Office per il Web con SharePoint Piano 2</span><span class="sxs-lookup"><span data-stu-id="9254a-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="9254a-153">SharePoint Online Piano 1</span><span class="sxs-lookup"><span data-stu-id="9254a-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="9254a-154">SharePoint Online Piano 2</span><span class="sxs-lookup"><span data-stu-id="9254a-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="9254a-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="9254a-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="9254a-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="9254a-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="9254a-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="9254a-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="9254a-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="9254a-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="9254a-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="9254a-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="9254a-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="9254a-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="9254a-161">Office 365 Extra File Storage è disponibile anche per i piani GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="9254a-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="9254a-162">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="9254a-162">Related content</span></span>

<span data-ttu-id="9254a-163">[Gestire i limiti di archiviazione del sito](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (articolo)</span><span class="sxs-lookup"><span data-stu-id="9254a-163">[Manage site storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="9254a-164">[Impostare lo spazio di archiviazione predefinito per gli utenti di OneDrive](/onedrive/set-default-storage-space)(articolo)</span><span class="sxs-lookup"><span data-stu-id="9254a-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>