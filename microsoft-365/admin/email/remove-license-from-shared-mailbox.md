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
ms.openlocfilehash: 873b50b34b9887ada92cc56f7083e3b748a52035
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327223"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="cb4e7-103">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cb4e7-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="cb4e7-104">Le cassette postali condivise in genere non richiedono una licenza.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="cb4e7-105">Seguire queste istruzioni per rimuovere una licenza da una cassetta postale condivisa in modo che sia possibile assegnarla a un utente o restituire la licenza in modo che non si paga per una licenza non necessaria.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="cb4e7-106">Una licenza è necessaria negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb4e7-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="cb4e7-107">La cassetta postale condivisa dispone di più di 50 GB di spazio di archiviazione in uso.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="cb4e7-108">La cassetta postale condivisa utilizza l'archiviazione sul posto.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="cb4e7-109">La cassetta postale condivisa viene messa in conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="cb4e7-110">Alla cassetta postale condivisa è assegnata una licenza di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="cb4e7-111">Rimuovere la licenza</span><span class="sxs-lookup"><span data-stu-id="cb4e7-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cb4e7-112">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cb4e7-113">È necessario rimuovere la licenza dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-113">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="cb4e7-114">Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-114">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="cb4e7-115">Selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-115">Select the shared mailbox.</span></span>

3. <span data-ttu-id="cb4e7-116">Nella scheda **Licenze e app** espandi **Licenze** e deseleziona la casella per la licenza che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-116">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="cb4e7-117">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-117">Select **Save changes**.</span></span>

5. <span data-ttu-id="cb4e7-118">Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**</span><span class="sxs-lookup"><span data-stu-id="cb4e7-118">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="cb4e7-119">Stai ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-119">You're still paying for the license.</span></span> <span data-ttu-id="cb4e7-120">Per interrompere il pagamento, [rimuovi la licenza dall'abbonamento.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="cb4e7-120">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="cb4e7-121">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb4e7-122">È necessario rimuovere la licenza dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-122">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="cb4e7-123">Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-123">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="cb4e7-124">Selezionare la cassetta postale condivisa, quindi selezionare **Modifica** accanto a **Licenze prodotto.**</span><span class="sxs-lookup"><span data-stu-id="cb4e7-124">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="cb4e7-125">Nella pagina **Licenze di** prodotto imposta l'interruttore su **Disattivato** per la licenza che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-125">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="cb4e7-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-126">Select **Save**.</span></span>

5. <span data-ttu-id="cb4e7-127">Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**</span><span class="sxs-lookup"><span data-stu-id="cb4e7-127">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="cb4e7-128">Stai ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-128">You're still paying for the license.</span></span> <span data-ttu-id="cb4e7-129">Per interrompere il pagamento, [rimuovi la licenza dall'abbonamento.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="cb4e7-129">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="cb4e7-130">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb4e7-131">È necessario rimuovere la licenza dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-131">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="cb4e7-132">Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-132">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="cb4e7-133">Selezionare la cassetta postale condivisa, quindi selezionare **Modifica** accanto a **Licenze prodotto.**</span><span class="sxs-lookup"><span data-stu-id="cb4e7-133">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="cb4e7-134">Nella pagina **Licenze di** prodotto imposta l'interruttore su **Disattivato** per la licenza che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-134">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="cb4e7-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-135">Select **Save**.</span></span>

5. <span data-ttu-id="cb4e7-136">Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**</span><span class="sxs-lookup"><span data-stu-id="cb4e7-136">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="cb4e7-137">Stai ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="cb4e7-137">You're still paying for the license.</span></span> <span data-ttu-id="cb4e7-138">Per interrompere il pagamento, [rimuovi la licenza dall'abbonamento.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="cb4e7-138">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="cb4e7-139">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="cb4e7-139">Related articles</span></span>

[<span data-ttu-id="cb4e7-140">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="cb4e7-140">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="cb4e7-141">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cb4e7-141">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="cb4e7-142">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cb4e7-142">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="cb4e7-143">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cb4e7-143">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="cb4e7-144">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="cb4e7-144">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)