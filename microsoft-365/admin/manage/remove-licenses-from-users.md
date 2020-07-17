---
title: Annullare l'assegnazione delle licenze agli utenti
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Informazioni su come annullare l'assegnazione delle licenze dagli account utente.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015936"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="c80c6-103">Annullare l'assegnazione delle licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="c80c6-103">Unassign licenses from users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c80c6-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="c80c6-104">The admin center is changing.</span></span> <span data-ttu-id="c80c6-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c80c6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="c80c6-106">È possibile annullare l'assegnazione delle licenze agli utenti nella pagina **utenti attivi** o nella pagina **licenze** .</span><span class="sxs-lookup"><span data-stu-id="c80c6-106">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="c80c6-107">Il metodo utilizzato varia a seconda che si desideri annullare l'assegnazione delle licenze di prodotto da utenti specifici o annullare l'assegnazione di licenze agli utenti da un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="c80c6-107">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="c80c6-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="c80c6-108">Before you begin</span></span>

- <span data-ttu-id="c80c6-109">Per annullare l'assegnazione delle licenze, è necessario essere un amministratore globale, una licenza per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="c80c6-110">Per ulteriori informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c80c6-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="c80c6-111">È possibile [rimuovere licenze da account utente con PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c80c6-111">You can [remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span></span>
- <span data-ttu-id="c80c6-112">È inoltre possibile [eliminare gli account utente](../add-users/delete-a-user.md) a cui è stata assegnata una licenza per rendere disponibile la propria licenza ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="c80c6-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="c80c6-113">Quando si elimina un account utente, la propria licenza è immediatamente disponibile per l'assegnazione a qualcun altro.</span><span class="sxs-lookup"><span data-stu-id="c80c6-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="c80c6-114">Utilizzare la pagina licenze per annullare l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="c80c6-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="c80c6-115">Quando si utilizza la pagina **licenze** per annullare l'assegnazione delle licenze, è necessario annullare l'assegnazione delle licenze per un prodotto specifico per un massimo di 20 utenti.</span><span class="sxs-lookup"><span data-stu-id="c80c6-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

1. <span data-ttu-id="c80c6-116">Nell'interfaccia di amministrazione, andare alla **Billing** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="c80c6-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="c80c6-117">Selezionare il prodotto per il quale si desidera annullare l'assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="c80c6-117">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="c80c6-118">Selezionare gli utenti per i quali si desidera annullare l'assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="c80c6-118">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="c80c6-119">Selezionare **Annulla assegnazione licenze**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-119">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="c80c6-120">Nella casella **Annulla assegnazione licenze** selezionare **Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-120">In the **Unassign licenses** box, select **Unassign**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="c80c6-121">Utilizzo della pagina utenti attivi per annullare l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="c80c6-121">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="c80c6-122">Quando si utilizza la pagina **utenti attivi** per annullare l'assegnazione delle licenze, è necessario annullare l'assegnazione delle licenze di prodotto dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="c80c6-122">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="c80c6-123">Annullamento dell'assegnazione delle licenze da un utente</span><span class="sxs-lookup"><span data-stu-id="c80c6-123">Unassign licenses from one user</span></span>
  
1. <span data-ttu-id="c80c6-124">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="c80c6-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c80c6-125">Selezionare la riga dell'utente per cui si desidera annullare l'assegnazione di una licenza.</span><span class="sxs-lookup"><span data-stu-id="c80c6-125">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="c80c6-126">Nel riquadro destro selezionare **Licenze e app**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-126">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="c80c6-127">Espandere la sezione **licenze** , deselezionare le caselle per le licenze che si desidera annullare l'assegnazione, quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-127">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="c80c6-128">Annullamento dell'assegnazione delle licenze da un utente</span><span class="sxs-lookup"><span data-stu-id="c80c6-128">Unassign licenses from one user</span></span>

1. <span data-ttu-id="c80c6-129">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="c80c6-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c80c6-130">Selezionare l'utente per il quale si desidera annullare l'assegnazione della licenza.</span><span class="sxs-lookup"><span data-stu-id="c80c6-130">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="c80c6-131">A destra, nella riga **licenze di prodotto** , selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-131">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="c80c6-132">Nel riquadro **licenze di prodotto** , impostare l'interruttore sulla posizione **disattivata** per la licenza che si desidera annullare l'assegnazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-132">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="c80c6-133">Ad esempio, se si disattiva la licenza di Office 365 Enterprise E3, la licenza verrà annienteta e tutti i servizi previsti dalla licenza per tale utente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-133">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="c80c6-134">Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-134">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="c80c6-135">Annullamento dell'assegnazione delle licenze da un utente</span><span class="sxs-lookup"><span data-stu-id="c80c6-135">Unassign licenses from one user</span></span>

1. <span data-ttu-id="c80c6-136">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="c80c6-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c80c6-137">Selezionare l'utente per il quale si desidera annullare l'assegnazione della licenza.</span><span class="sxs-lookup"><span data-stu-id="c80c6-137">Pick the user that you want to unassign the license for.</span></span>
3. <span data-ttu-id="c80c6-138">A destra, nella riga **licenze di prodotto** , selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-138">On the right, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="c80c6-139">Nel riquadro **licenze di prodotto** , impostare l'interruttore sulla posizione **disattivata** per la licenza che si desidera annullare l'assegnazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-139">In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to unassign for the user.</span></span> <span data-ttu-id="c80c6-140">Ad esempio, se si disattiva la licenza di Office 365 Enterprise E3, la licenza verrà annienteta e tutti i servizi previsti dalla licenza per tale utente.</span><span class="sxs-lookup"><span data-stu-id="c80c6-140">For example, if you switch off the Office 365 Enterprise E3 license, it unassigns that license and all services under that license for that user.</span></span>
5. <span data-ttu-id="c80c6-141">Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-141">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="c80c6-142">Annullamento dell'assegnazione delle licenze da più utenti</span><span class="sxs-lookup"><span data-stu-id="c80c6-142">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="c80c6-143">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="c80c6-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c80c6-144">Selezionare i cerchi accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="c80c6-144">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="c80c6-145">Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-145">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="c80c6-146">Nel riquadro **Gestisci licenze prodotto** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-146">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c80c6-147">Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la casella di controllo **Rimuovi tutte le licenze di prodotto dagli utenti selezionati** e quindi fare clic su **Sostituisci** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-147">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="c80c6-148">Annullamento dell'assegnazione delle licenze da più utenti</span><span class="sxs-lookup"><span data-stu-id="c80c6-148">Unassign licenses from multiple users</span></span>

1. <span data-ttu-id="c80c6-149">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="c80c6-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c80c6-150">Selezionare le caselle accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione di tutte le licenze.</span><span class="sxs-lookup"><span data-stu-id="c80c6-150">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="c80c6-151">Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-151">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="c80c6-152">Nel riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-152">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c80c6-153">Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la casella di controllo **Rimuovi tutte le licenze di prodotto dagli utenti selezionati** , quindi selezionare **Sostituisci** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-153">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="c80c6-154">Annullamento dell'assegnazione delle licenze da più utenti</span><span class="sxs-lookup"><span data-stu-id="c80c6-154">Unassign licenses from multiple users</span></span>
  
1. <span data-ttu-id="c80c6-155">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="c80c6-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c80c6-156">Selezionare le caselle accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione di tutte le licenze.</span><span class="sxs-lookup"><span data-stu-id="c80c6-156">Select the boxes next to the names of the users that you want to unassign all licenses for.</span></span>
3. <span data-ttu-id="c80c6-157">Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-157">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="c80c6-158">Nel riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-158">In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="c80c6-159">Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la casella di controllo **Rimuovi tutte le licenze di prodotto dagli utenti selezionati** , quindi selezionare **Sostituisci** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c80c6-159">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="c80c6-160">Cosa succede ai dati di un utente quando si rimuove la licenza?</span><span class="sxs-lookup"><span data-stu-id="c80c6-160">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="c80c6-161">Quando una licenza viene rimossa da un utente, i dati associati a quell'account vengono conservati per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="c80c6-161">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="c80c6-162">Dopo il periodo di tolleranza di 30 giorni, i dati vengono eliminati e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="c80c6-162">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="c80c6-163">I file salvati in OneDrive for business non vengono eliminati, a meno che l'utente non venga eliminato dall'interfaccia di amministrazione di Microsoft 365 o venga rimosso tramite la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c80c6-163">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="c80c6-164">Per ulteriori informazioni, vedere [OneDrive retention and Deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span><span class="sxs-lookup"><span data-stu-id="c80c6-164">For more information, see [OneDrive retention and deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="c80c6-165">Quando la licenza è stata rimossa, la cassetta postale dell'utente non è più disponibile per la ricerca tramite uno strumento di eDiscovery, ad esempio ricerca contenuto o Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c80c6-165">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="c80c6-166">Per ulteriori informazioni, vedere la sezione relativa alla ricerca di cassette postali disconnesse o concessi in licenza in [Ricerca contenuto in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="c80c6-166">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).</span></span>
- <span data-ttu-id="c80c6-167">Se si dispone di un abbonamento Enterprise, ad esempio Office 365 Enterprise E3, Exchange Online consente di mantenere i dati della cassetta postale di un account utente eliminato utilizzando le [cassette postali inattive](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="c80c6-167">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span> <span data-ttu-id="c80c6-168">Per ulteriori informazioni, vedere [creare e gestire le cassette postali inattive in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="c80c6-168">For more information, see [Create and manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).</span></span>
- <span data-ttu-id="c80c6-169">Per informazioni su come bloccare l'accesso di un utente ai dati di Microsoft 365 dopo che la licenza è stata rimossa e come ottenere l'accesso ai dati successivamente, vedere [Remove an ex Employee](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="c80c6-169">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="c80c6-170">Se si rimuove la licenza di un utente e le app di Office sono ancora installate, vedranno gli [errori di attivazione e di prodotto senza licenza in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) quando utilizzano le app di Office.</span><span class="sxs-lookup"><span data-stu-id="c80c6-170">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c80c6-171">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c80c6-171">Next steps</span></span>

<span data-ttu-id="c80c6-172">Se non si intende [riassegnare le licenze inutilizzate ad altri utenti](../../managed-desktop/get-started/assign-licenses.md), prendere in considerazione la possibilità di [rimuovere le licenze dall'abbonamento](../../commerce/licenses/buy-licenses.md) in modo che non vengano pagate più licenze di quante ne siano necessarie.</span><span class="sxs-lookup"><span data-stu-id="c80c6-172">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="c80c6-173">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="c80c6-173">Related content</span></span>

<span data-ttu-id="c80c6-174">[Rimuovere le licenze dall'abbonamento](../../commerce/licenses/remove-licenses-from-subscription.md) (articolo) </span><span class="sxs-lookup"><span data-stu-id="c80c6-174">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="c80c6-175">[Assegnare licenze agli utenti](assign-licenses-to-users.md) (articolo) </span><span class="sxs-lookup"><span data-stu-id="c80c6-175">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="c80c6-176">[Informazioni su abbonamenti e licenze in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c80c6-176">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>