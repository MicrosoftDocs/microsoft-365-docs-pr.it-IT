---
title: Risoluzione dei conflitti di licenze
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Informazioni su come risolvere i conflitti di licenza con l'abbonamento a Microsoft 365 for business.
ms.openlocfilehash: 7d7da843ba747679f36539bcf920b1b9b2b7ad28
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139578"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="47f8d-103">Risoluzione dei conflitti di licenze</span><span class="sxs-lookup"><span data-stu-id="47f8d-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="47f8d-104">L'interfaccia di amministrazione cambia.</span><span class="sxs-lookup"><span data-stu-id="47f8d-104">The admin center is changing.</span></span> <span data-ttu-id="47f8d-105">Se l'esperienza non corrisponde ai dettagli presentati, vedere [About The New Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="47f8d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="47f8d-106">È consigliabile acquistare le licenze necessarie per l'abbonamento prima di creare nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="47f8d-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="47f8d-107">In questo modo, quando si creano gli account utente sarà possibile assegnare una licenza ai nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="47f8d-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="47f8d-108">Se tutte le licenze disponibili sono già state assegnate agli utenti, ma alcune di esse sono scadute, oppure se si prova a rimuovere una licenza già assegnata a un utente, si verificheranno conflitti di licenza.</span><span class="sxs-lookup"><span data-stu-id="47f8d-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="47f8d-109">Per ulteriori informazioni, vedere [rimuovere licenze dall'abbonamento](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="47f8d-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="47f8d-110">Come si visualizzano i conflitti di licenza?</span><span class="sxs-lookup"><span data-stu-id="47f8d-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="47f8d-111">Nell'interfaccia di amministrazione, andare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="47f8d-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="47f8d-112">Nell'interfaccia di amministrazione, andare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="47f8d-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="47f8d-113">Nell'interfaccia di amministrazione, andare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="47f8d-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="47f8d-114">Osservare la colonna **Stato** per informazioni sul conflitto.</span><span class="sxs-lookup"><span data-stu-id="47f8d-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="47f8d-115">Se si verifica un conflitto, verrà visualizzato un messaggio di avviso che indica che uno o più utenti hanno bisogno di una licenza valida.</span><span class="sxs-lookup"><span data-stu-id="47f8d-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="47f8d-116">Se non è presente alcun conflitto, la colonna **Stato** non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="47f8d-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="47f8d-117">Come si risolvono i conflitti di licenza?</span><span class="sxs-lookup"><span data-stu-id="47f8d-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="47f8d-118">È possibile risolvere i conflitti di licenza [acquistando più licenze](../../commerce/licenses/buy-licenses.md) o [rimuovendo le licenze dagli utenti che non ne hanno più bisogno](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="47f8d-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="47f8d-119">È possibile [eliminare un account utente per liberare una licenza](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="47f8d-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="47f8d-120">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="47f8d-120">Related articles</span></span> 

<span data-ttu-id="47f8d-121">[Assegnazione licenze agli utenti](assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="47f8d-121">[Assign licenses to users](assign-licenses-to-users.md)</span></span>
  
[<span data-ttu-id="47f8d-122">Rimuovere licenze dagli utenti</span><span class="sxs-lookup"><span data-stu-id="47f8d-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
