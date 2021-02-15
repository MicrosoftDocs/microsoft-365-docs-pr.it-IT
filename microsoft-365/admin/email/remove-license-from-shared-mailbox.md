---
title: Rimuovere una licenza da cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698304"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="9a498-103">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="9a498-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9a498-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="9a498-104">The admin center is changing.</span></span> <span data-ttu-id="9a498-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="9a498-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="9a498-106">Le cassette postali condivise in genere non richiedono una licenza.</span><span class="sxs-lookup"><span data-stu-id="9a498-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="9a498-107">Seguire queste istruzioni per rimuovere una licenza da una cassetta postale condivisa, in modo da poterla assegnare a un utente o restituire la licenza in modo da non pagare una licenza non necessaria.</span><span class="sxs-lookup"><span data-stu-id="9a498-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="9a498-108">Una licenza è necessaria negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a498-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="9a498-109">La cassetta postale condivisa dispone di più di 50 GB di spazio di archiviazione in uso.</span><span class="sxs-lookup"><span data-stu-id="9a498-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="9a498-110">La cassetta postale condivisa utilizza l'archiviazione sul posto.</span><span class="sxs-lookup"><span data-stu-id="9a498-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="9a498-111">La cassetta postale condivisa viene conservata per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="9a498-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="9a498-112">Alla cassetta postale condivisa è assegnata una licenza di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9a498-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="9a498-113">Rimuovere la licenza</span><span class="sxs-lookup"><span data-stu-id="9a498-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9a498-114">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="9a498-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9a498-115">È necessario rimuovere la licenza dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="9a498-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="9a498-116">Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9a498-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="9a498-117">Selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="9a498-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="9a498-118">Nella scheda **Licenze e app** espandi **Licenze** e deseleziona la casella per la licenza che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9a498-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="9a498-119">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="9a498-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="9a498-120">Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**</span><span class="sxs-lookup"><span data-stu-id="9a498-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="9a498-121">Stai ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="9a498-121">You're still paying for the license.</span></span> <span data-ttu-id="9a498-122">Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="9a498-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="9a498-123">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="9a498-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a498-124">È necessario rimuovere la licenza dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="9a498-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="9a498-125">Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9a498-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="9a498-126">Selezionare la cassetta postale condivisa, quindi selezionare **Modifica** accanto a **Licenze di prodotto.**</span><span class="sxs-lookup"><span data-stu-id="9a498-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="9a498-127">Nella pagina **Licenze di** prodotto imposta l'interruttore su **Disattivato** per la licenza che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9a498-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="9a498-128">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9a498-128">Select **Save**.</span></span>

5. <span data-ttu-id="9a498-129">Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**</span><span class="sxs-lookup"><span data-stu-id="9a498-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="9a498-130">Stai ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="9a498-130">You're still paying for the license.</span></span> <span data-ttu-id="9a498-131">Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="9a498-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="9a498-132">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="9a498-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a498-133">È necessario rimuovere la licenza dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="9a498-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="9a498-134">Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9a498-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="9a498-135">Selezionare la cassetta postale condivisa, quindi selezionare **Modifica** accanto a **Licenze di prodotto.**</span><span class="sxs-lookup"><span data-stu-id="9a498-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="9a498-136">Nella pagina **Licenze di** prodotto imposta l'interruttore su **Disattivato** per la licenza che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9a498-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="9a498-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9a498-137">Select **Save**.</span></span>

5. <span data-ttu-id="9a498-138">Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**</span><span class="sxs-lookup"><span data-stu-id="9a498-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="9a498-139">Stai ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="9a498-139">You're still paying for the license.</span></span> <span data-ttu-id="9a498-140">Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="9a498-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="9a498-141">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="9a498-141">Related articles</span></span>

[<span data-ttu-id="9a498-142">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="9a498-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="9a498-143">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="9a498-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="9a498-144">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="9a498-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="9a498-145">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="9a498-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="9a498-146">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="9a498-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
