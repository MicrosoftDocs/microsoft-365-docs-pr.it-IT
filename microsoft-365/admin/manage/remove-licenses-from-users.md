---
title: Annullare l'assegnazione delle licenze agli utenti
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Informazioni su come annullare l'assegnazione delle licenze dagli account utente.
ms.date: 07/01/2020
ms.openlocfilehash: 6f2cbf65e1d6a38a4b1ed00976d4dd473d7331e9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332415"
---
# <a name="unassign-licenses-from-users"></a><span data-ttu-id="089e0-103">Annullare l'assegnazione delle licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="089e0-103">Unassign licenses from users</span></span>

<span data-ttu-id="089e0-104">È possibile annullare l'assegnazione delle licenze dagli utenti nella **pagina Utenti** attivi o nella **pagina Licenze.**</span><span class="sxs-lookup"><span data-stu-id="089e0-104">You can unassign licenses from users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="089e0-105">Il metodo utilizzato dipende dal fatto che si desideri annullare l'assegnazione delle licenze di prodotto da utenti specifici o annullare l'assegnazione delle licenze degli utenti da un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="089e0-105">The method you use depends on whether you want to unassign product licenses from specific users or unassign users licenses from a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="089e0-106">Gli amministratori non possono assegnare o annullare l'assegnazione di licenze per un abbonamento acquistato in modalità self-service da un utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="089e0-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="089e0-107">È possibile [assumere il controllo di un abbonamento acquistato in modalità self-service](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) e quindi assegnare licenze o annullarne l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="089e0-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="089e0-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="089e0-108">Before you begin</span></span>

- <span data-ttu-id="089e0-109">Per annullare l'assegnazione delle licenze, devi essere un amministratore globale, di licenza e utente.</span><span class="sxs-lookup"><span data-stu-id="089e0-109">You must be a Global, License, User admin to unassign licenses.</span></span> <span data-ttu-id="089e0-110">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="089e0-110">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="089e0-111">È possibile [rimuovere licenze da account utente con PowerShell di Office 365](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="089e0-111">You can [remove licenses from user accounts with Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="089e0-112">È inoltre possibile [eliminare gli account utente](../add-users/delete-a-user.md) a cui è stata assegnata una licenza per rendere disponibile la licenza ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="089e0-112">You can also [delete user accounts](../add-users/delete-a-user.md) that were assigned a license to make their license available to other users.</span></span> <span data-ttu-id="089e0-113">Quando elimini un account utente, la relativa licenza è immediatamente disponibile per l'assegnazione a qualcun altro.</span><span class="sxs-lookup"><span data-stu-id="089e0-113">When you delete a user account, their license is immediately available to assign to someone else.</span></span>

## <a name="use-the-licenses-page-to-unassign-licenses"></a><span data-ttu-id="089e0-114">Usare la pagina Licenze per annullare l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="089e0-114">Use the Licenses page to unassign licenses</span></span>

<span data-ttu-id="089e0-115">Quando si utilizza la **pagina Licenze** per annullare l'assegnazione delle licenze, si annulla l'assegnazione delle licenze per un prodotto specifico per un massimo di 20 utenti.</span><span class="sxs-lookup"><span data-stu-id="089e0-115">When you use the **Licenses** page to unassign licenses, you unassign licenses for a specific product for up to 20 users.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="089e0-116">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="089e0-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="089e0-117">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="089e0-117">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="089e0-118">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="089e0-118">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="089e0-119">Selezionare il prodotto per cui si desidera annullare l'assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="089e0-119">Select the product for which you want to unassign licenses.</span></span>
3. <span data-ttu-id="089e0-120">Selezionare gli utenti per i quali si desidera annullare l'assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="089e0-120">Select the users for which you want to unassign licenses.</span></span>
4. <span data-ttu-id="089e0-121">Selezionare **Annulla assegnazione licenze**.</span><span class="sxs-lookup"><span data-stu-id="089e0-121">Select **Unassign licenses**.</span></span>
5. <span data-ttu-id="089e0-122">Nella casella **Annulla assegnazione licenze** selezionare Annulla **assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="089e0-122">In the **Unassign licenses** box, select **Unassign**.</span></span>

## <a name="use-the-active-users-page-to-unassign-licenses"></a><span data-ttu-id="089e0-123">Usare la pagina Utenti attivi per annullare l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="089e0-123">Use the Active users page to unassign licenses</span></span>

<span data-ttu-id="089e0-124">Quando si utilizza la **pagina Utenti attivi** per annullare l'assegnazione delle licenze, si annullano le licenze di prodotto dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="089e0-124">When you use the **Active users** page to unassign licenses, you unassign product licenses from users.</span></span>

### <a name="unassign-licenses-from-one-user"></a><span data-ttu-id="089e0-125">Annullare l'assegnazione delle licenze da un utente</span><span class="sxs-lookup"><span data-stu-id="089e0-125">Unassign licenses from one user</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="089e0-126">Nell'interfaccia di amministrazione passare alla pagina **Utenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="089e0-126">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="089e0-127">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="089e0-127">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="089e0-128">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="089e0-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="089e0-129">Selezionare la riga dell'utente per cui si desidera annullare l'assegnazione di una licenza.</span><span class="sxs-lookup"><span data-stu-id="089e0-129">Select the row of the user that you want to unassign a license for.</span></span>
3. <span data-ttu-id="089e0-130">Nel riquadro destro selezionare **Licenze e app**.</span><span class="sxs-lookup"><span data-stu-id="089e0-130">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="089e0-131">Espandere la **sezione** Licenze, deselezionare le caselle relative alle licenze che si desidera annullare l'assegnazione, quindi selezionare **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="089e0-131">Expand the **Licenses** section, clear the boxes for the licenses that you want to unassign, then select **Save changes**.</span></span>

### <a name="unassign-licenses-from-multiple-users"></a><span data-ttu-id="089e0-132">Annullare l'assegnazione delle licenze da più utenti</span><span class="sxs-lookup"><span data-stu-id="089e0-132">Unassign licenses from multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="089e0-133">Nell'interfaccia di amministrazione passare alla pagina **Utenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="089e0-133">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="089e0-134">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="089e0-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="089e0-135">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="089e0-135">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="089e0-136">Selezionare i cerchi accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="089e0-136">Select the circles next to the names of the users that you want to unassign licenses for.</span></span>
3. <span data-ttu-id="089e0-137">Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.</span><span class="sxs-lookup"><span data-stu-id="089e0-137">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="089e0-138">Nel riquadro **Gestisci licenze prodotto** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="089e0-138">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="089e0-139">Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la **casella** di controllo Rimuovi tutte le licenze di prodotto dagli utenti selezionati, quindi **selezionare Sostituisci** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="089e0-139">At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.</span></span>

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a><span data-ttu-id="089e0-140">Cosa succede ai dati di un utente quando si rimuove la licenza?</span><span class="sxs-lookup"><span data-stu-id="089e0-140">What happens to a user's data when you remove their license?</span></span>

- <span data-ttu-id="089e0-141">Quando una licenza viene rimossa da un utente, i dati associati a tale account vengono mantenuti per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="089e0-141">When a license is removed from a user, data that is associated with that account is held for 30 days.</span></span> <span data-ttu-id="089e0-142">Dopo il periodo di tolleranza di 30 giorni, i dati vengono eliminati e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="089e0-142">After the 30-day grace period, the data is deleted and can't be recovered.</span></span>
- <span data-ttu-id="089e0-143">I file salvati in OneDrive for Business non vengono eliminati a meno che l'utente non venga eliminato dall'interfaccia di amministrazione di Microsoft 365 o non venga rimosso tramite la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="089e0-143">Files saved in OneDrive for Business aren't deleted unless the user is deleted from the Microsoft 365 admin center or is removed through Active Directory synchronization.</span></span> <span data-ttu-id="089e0-144">Per ulteriori informazioni, vedere Conservazione ed eliminazione [di OneDrive.](/onedrive/retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="089e0-144">For more information, see [OneDrive retention and deletion](/onedrive/retention-and-deletion).</span></span>
- <span data-ttu-id="089e0-145">Quando la licenza viene rimossa, la cassetta postale dell'utente non è più disponibile per la ricerca tramite uno strumento di eDiscovery, ad esempio Ricerca contenuto o Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="089e0-145">When the license is removed, the user's mailbox is no longer searchable by using an eDiscovery tool such as Content Search or Advanced eDiscovery.</span></span> <span data-ttu-id="089e0-146">Per ulteriori informazioni, vedere "Ricerca di cassette postali disconnesse o senza licenza" in [Ricerca contenuto in Microsoft 365.](../../compliance/content-search.md)</span><span class="sxs-lookup"><span data-stu-id="089e0-146">For more information, see "Searching disconnected or de-licensed mailboxes" in [Content Search in Microsoft 365](../../compliance/content-search.md).</span></span>
- <span data-ttu-id="089e0-147">Se si dispone di un abbonamento Enterprise, come Office 365 Enterprise E3, Exchange Online consente di conservare i dati delle cassette postali di un account utente eliminato utilizzando cassette postali [inattive.](../../compliance/inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="089e0-147">If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted user account by using [inactive mailboxes](../../compliance/inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="089e0-148">Per ulteriori informazioni, vedere [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="089e0-148">For more information, see [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).</span></span>
- <span data-ttu-id="089e0-149">Per informazioni su come bloccare l'accesso di un utente ai dati di Microsoft 365 dopo la rimozione della licenza e su come ottenere l'accesso ai dati in seguito, vedere Rimuovere un [ex dipendente.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="089e0-149">To learn how to block a user's access to Microsoft 365 data after their license is removed, and how to get access to the data afterwards, see [Remove a former employee](../add-users/remove-former-employee.md).</span></span>
- <span data-ttu-id="089e0-150">Se si rimuove la licenza di un utente e le app di Office sono ancora installate, vengono visualizzati errori di attivazione e prodotto senza licenza [in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) quando usano le app di Office.</span><span class="sxs-lookup"><span data-stu-id="089e0-150">If you remove a user's license and they still have Office apps installed, they see [Unlicensed Product and activation errors in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) when they use Office apps.</span></span>

## <a name="next-steps"></a><span data-ttu-id="089e0-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="089e0-151">Next steps</span></span>

<span data-ttu-id="089e0-152">Se non si desidera [riassegnare](../../managed-desktop/get-started/assign-licenses.md)le licenze non utilizzate [](../../commerce/licenses/buy-licenses.md) ad altri utenti, è consigliabile rimuovere le licenze dall'abbonamento in modo da non pagare più licenze di quelle necessarie.</span><span class="sxs-lookup"><span data-stu-id="089e0-152">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="089e0-153">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="089e0-153">Related content</span></span>

<span data-ttu-id="089e0-154">[Rimuovere licenze dall'abbonamento](../../commerce/licenses/buy-licenses.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="089e0-154">[Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>\
<span data-ttu-id="089e0-155">[Assegnare licenze agli utenti](assign-licenses-to-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="089e0-155">[Assign licenses to users](assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="089e0-156">[Informazioni su abbonamenti e licenze in Microsoft 365 per le aziende](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="089e0-156">[Understand subscriptions and licenses in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>
