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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Informazioni su come risolvere i conflitti di licenza con l'abbonamento a Microsoft 365 for business.
ms.openlocfilehash: 05efe9e75b051ece900ba9defe047f1244b713a9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399669"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="70329-103">Risoluzione dei conflitti di licenze</span><span class="sxs-lookup"><span data-stu-id="70329-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="70329-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="70329-104">The admin center is changing.</span></span> <span data-ttu-id="70329-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="70329-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="70329-106">È consigliabile acquistare le licenze necessarie per l'abbonamento prima di creare nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="70329-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="70329-107">In questo modo, quando si creano gli account utente sarà possibile assegnare una licenza ai nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="70329-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="70329-108">Se tutte le licenze disponibili sono già state assegnate agli utenti, ma alcune di esse sono scadute, oppure se si prova a rimuovere una licenza già assegnata a un utente, si verificheranno conflitti di licenza.</span><span class="sxs-lookup"><span data-stu-id="70329-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="70329-109">Per ulteriori informazioni, vedere [rimuovere licenze dall'abbonamento](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="70329-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="70329-110">Come si visualizzano i conflitti di licenza?</span><span class="sxs-lookup"><span data-stu-id="70329-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="70329-111">Nell'interfaccia di amministrazione, andare alla **Billing** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="70329-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="70329-112">Nell'interfaccia di amministrazione, andare alla **Billing** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="70329-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="70329-113">Nell'interfaccia di amministrazione, andare alla **Billing** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="70329-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="70329-114">Osservare la colonna **Stato** per informazioni sul conflitto.</span><span class="sxs-lookup"><span data-stu-id="70329-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="70329-115">Se si verifica un conflitto, verrà visualizzato un messaggio di avviso che indica che uno o più utenti hanno bisogno di una licenza valida.</span><span class="sxs-lookup"><span data-stu-id="70329-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70329-116">Se non è presente alcun conflitto, la colonna **Stato** non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="70329-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="70329-117">Come si risolvono i conflitti di licenza?</span><span class="sxs-lookup"><span data-stu-id="70329-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="70329-118">È possibile risolvere i conflitti di licenza [acquistando più licenze](../../commerce/licenses/buy-licenses.md) o [rimuovendo le licenze dagli utenti che non ne hanno più bisogno](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="70329-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="70329-119">È possibile [eliminare un account utente per liberare una licenza](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="70329-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="70329-120">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="70329-120">Related articles</span></span> 

<span data-ttu-id="70329-121">[Assegnazione licenze agli utenti](assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="70329-121">[Assign licenses to users](assign-licenses-to-users.md)</span></span>
  
[<span data-ttu-id="70329-122">Rimuovere licenze dagli utenti</span><span class="sxs-lookup"><span data-stu-id="70329-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
