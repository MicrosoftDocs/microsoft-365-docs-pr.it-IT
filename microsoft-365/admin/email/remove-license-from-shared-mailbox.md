---
title: Rimuovere una licenza da cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Rimuovere la licenza da una cassetta postale condivisa per assegnarla a un altro utente. '
ms.openlocfilehash: 401b334efeccf6d7c4caca20be3cc9767b2df945
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432220"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="4d92f-103">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="4d92f-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4d92f-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="4d92f-104">The admin center is changing.</span></span> <span data-ttu-id="4d92f-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="4d92f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4d92f-106">Le cassette postali condivise in genere non richiedono una licenza.</span><span class="sxs-lookup"><span data-stu-id="4d92f-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="4d92f-107">Seguire le istruzioni riportate di seguito per rimuovere una licenza da una cassetta postale condivisa in modo che sia possibile assegnarla a un utente oppure restituire la licenza in modo che non si paghi una licenza di cui non si ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="4d92f-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="4d92f-108">È necessaria una licenza negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d92f-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="4d92f-109">La cassetta postale condivisa ha più di 50 GB di spazio di archiviazione in uso.</span><span class="sxs-lookup"><span data-stu-id="4d92f-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="4d92f-110">La cassetta postale condivisa utilizza l'archiviazione sul posto.</span><span class="sxs-lookup"><span data-stu-id="4d92f-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="4d92f-111">La cassetta postale condivisa viene messa in blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="4d92f-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="4d92f-112">Rimuovere la licenza</span><span class="sxs-lookup"><span data-stu-id="4d92f-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d92f-113">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d92f-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4d92f-114">È necessario rimuovere la licenza dalla pagina utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="4d92f-114">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="4d92f-115">Non è possibile rimuovere la licenza dalla pagina della cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="4d92f-115">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="4d92f-116">Selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="4d92f-116">Select the shared mailbox.</span></span>

3. <span data-ttu-id="4d92f-117">Una scheda **licenze e app** , espandere **licenze** e deselezionare la casella per la licenza che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="4d92f-117">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="4d92f-118">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-118">Select **Save changes**.</span></span>

5. <span data-ttu-id="4d92f-119">Quando si torna alla pagina **utenti attivi** , lo stato della cassetta postale condivisa non verrà **concesso in licenza**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-119">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="4d92f-120">Si sta ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="4d92f-120">You're still paying for the license.</span></span> <span data-ttu-id="4d92f-121">Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="4d92f-121">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="4d92f-122">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d92f-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4d92f-123">È necessario rimuovere la licenza dalla pagina utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="4d92f-123">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="4d92f-124">Non è possibile rimuovere la licenza dalla pagina della cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="4d92f-124">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="4d92f-125">Selezionare la cassetta postale condivisa e quindi fare clic su **modifica** accanto a **licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-125">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="4d92f-126">Una pagina **licenze di prodotto** , impostare l'interruttore su **disattivato** per la licenza che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="4d92f-126">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="4d92f-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-127">Select **Save**.</span></span>

5. <span data-ttu-id="4d92f-128">Quando si torna alla pagina **utenti attivi** , lo stato della cassetta postale condivisa non verrà **concesso in licenza**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-128">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="4d92f-129">Si sta ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="4d92f-129">You're still paying for the license.</span></span> <span data-ttu-id="4d92f-130">Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="4d92f-130">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="4d92f-131">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d92f-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4d92f-132">È necessario rimuovere la licenza dalla pagina utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="4d92f-132">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="4d92f-133">Non è possibile rimuovere la licenza dalla pagina della cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="4d92f-133">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="4d92f-134">Selezionare la cassetta postale condivisa e quindi fare clic su **modifica** accanto a **licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-134">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="4d92f-135">Una pagina **licenze di prodotto** , impostare l'interruttore su **disattivato** per la licenza che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="4d92f-135">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="4d92f-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-136">Select **Save**.</span></span>

5. <span data-ttu-id="4d92f-137">Quando si torna alla pagina **utenti attivi** , lo stato della cassetta postale condivisa non verrà **concesso in licenza**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-137">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="4d92f-138">Si sta ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="4d92f-138">You're still paying for the license.</span></span> <span data-ttu-id="4d92f-139">Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="4d92f-139">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="4d92f-140">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="4d92f-140">Related articles</span></span>

[<span data-ttu-id="4d92f-141">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="4d92f-141">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="4d92f-142">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="4d92f-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="4d92f-143">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="4d92f-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="4d92f-144">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="4d92f-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="4d92f-145">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="4d92f-145">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
