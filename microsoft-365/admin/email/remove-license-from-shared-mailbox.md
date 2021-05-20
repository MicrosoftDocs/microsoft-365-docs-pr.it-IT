---
title: Rimuovere una licenza da cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Rimuovere la licenza da una cassetta postale condivisa per assegnarla a un altro utente. '
ms.openlocfilehash: d552cfb77ff0ab2853939c6cb25fd4737f8c17d3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537584"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="47076-103">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="47076-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="47076-104">Le cassette postali condivise in genere non richiedono una licenza.</span><span class="sxs-lookup"><span data-stu-id="47076-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="47076-105">Seguire queste istruzioni per rimuovere una licenza da una cassetta postale condivisa in modo che sia possibile assegnarla a un utente o restituire la licenza in modo che non si paga per una licenza non necessaria.</span><span class="sxs-lookup"><span data-stu-id="47076-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="47076-106">Una licenza è necessaria negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="47076-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="47076-107">La cassetta postale condivisa dispone di più di 50 GB di spazio di archiviazione in uso.</span><span class="sxs-lookup"><span data-stu-id="47076-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="47076-108">La cassetta postale condivisa utilizza l'archiviazione sul posto.</span><span class="sxs-lookup"><span data-stu-id="47076-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="47076-109">La cassetta postale condivisa viene messa in conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="47076-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="47076-110">Alla cassetta postale condivisa è assegnata una licenza di Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="47076-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="47076-111">Rimuovere la licenza</span><span class="sxs-lookup"><span data-stu-id="47076-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="47076-112">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="47076-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="47076-113">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="47076-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="47076-114">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="47076-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

   > [!NOTE]
   > <span data-ttu-id="47076-115">È necessario rimuovere la licenza dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="47076-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="47076-116">Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="47076-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="47076-117">Selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="47076-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="47076-118">Nella scheda **Licenze e app** espandi **Licenze** e deseleziona la casella per la licenza che vuoi rimuovere.</span><span class="sxs-lookup"><span data-stu-id="47076-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="47076-119">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="47076-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="47076-120">Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**</span><span class="sxs-lookup"><span data-stu-id="47076-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="47076-121">Stai ancora pagando la licenza.</span><span class="sxs-lookup"><span data-stu-id="47076-121">You're still paying for the license.</span></span> <span data-ttu-id="47076-122">Per interrompere il pagamento, [rimuovi la licenza dall'abbonamento.](../../commerce/licenses/buy-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="47076-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="47076-123">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="47076-123">Related articles</span></span>

[<span data-ttu-id="47076-124">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="47076-124">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="47076-125">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="47076-125">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="47076-126">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="47076-126">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="47076-127">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="47076-127">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="47076-128">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="47076-128">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
