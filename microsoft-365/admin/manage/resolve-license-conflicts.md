---
title: Risoluzione dei conflitti di licenze
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Informazioni su come risolvere i conflitti di licenza con l'abbonamento a Microsoft 365 per le aziende.
ms.openlocfilehash: 284a6b169c02314dd2bbd0e13c10c081cb50f58d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114454"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="b0fa2-103">Risoluzione dei conflitti di licenze</span><span class="sxs-lookup"><span data-stu-id="b0fa2-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b0fa2-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-104">The admin center is changing.</span></span> <span data-ttu-id="b0fa2-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="b0fa2-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="b0fa2-106">È consigliabile acquistare le licenze necessarie per l'abbonamento prima di creare nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="b0fa2-107">In questo modo, quando si creano gli account utente sarà possibile assegnare una licenza ai nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="b0fa2-108">Se tutte le licenze disponibili sono già state assegnate agli utenti, ma alcune di esse sono scadute, oppure se si prova a rimuovere una licenza già assegnata a un utente, si verificheranno conflitti di licenza.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="b0fa2-109">Per ulteriori informazioni, vedere [Rimuovere licenze dall'abbonamento.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="b0fa2-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="b0fa2-110">Come si visualizzano i conflitti di licenza?</span><span class="sxs-lookup"><span data-stu-id="b0fa2-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b0fa2-111">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b0fa2-112">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b0fa2-113">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="b0fa2-114">Osservare la colonna **Stato** per informazioni sul conflitto.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="b0fa2-115">In caso di conflitto, verrà visualizzato un messaggio di avviso che indica che uno o più utenti necessitano di una licenza valida.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0fa2-116">Se non è presente alcun conflitto, la colonna **Stato** non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="b0fa2-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="b0fa2-117">Come si risolvono i conflitti di licenza?</span><span class="sxs-lookup"><span data-stu-id="b0fa2-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="b0fa2-118">È possibile risolvere i conflitti di licenza [acquistando](../../commerce/licenses/buy-licenses.md) altre licenze o rimuovendo le licenze dagli utenti [che non ne hanno più bisogno.](remove-licenses-from-users.md)</span><span class="sxs-lookup"><span data-stu-id="b0fa2-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="b0fa2-119">È possibile [eliminare un account utente per liberare una licenza](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="b0fa2-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="b0fa2-120">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b0fa2-120">Related articles</span></span>

<span data-ttu-id="b0fa2-121">[Assegnazione licenze agli utenti](assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="b0fa2-121">[Assign licenses to users](assign-licenses-to-users.md)</span></span>
  
[<span data-ttu-id="b0fa2-122">Rimuovere licenze dagli utenti</span><span class="sxs-lookup"><span data-stu-id="b0fa2-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
