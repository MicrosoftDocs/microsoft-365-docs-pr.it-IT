---
title: Gestire le richieste di licenza
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Informazioni su come esaminare e approvare o rifiutare le richieste di licenza degli utenti per l'abbonamento a Microsoft 365 per le aziende.
ms.date: 08/07/2020
ms.openlocfilehash: 06ee210b39c19c1f2c8a2041c463568e55001b6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331551"
---
# <a name="manage-license-requests"></a><span data-ttu-id="f705e-103">Gestire le richieste di licenza</span><span class="sxs-lookup"><span data-stu-id="f705e-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="f705e-104">Le informazioni contenute in questo articolo si applicano solo ai prodotti acquistati in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="f705e-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="f705e-105">Per ulteriori informazioni, vedere [Domande frequenti sugli acquisti in self-service.](../subscriptions/self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="f705e-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="f705e-106">Se si disabilitano gli acquisti in modalità self-service nell'organizzazione, è possibile utilizzare le richieste di licenze per gestire il processo di richiesta di licenza per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f705e-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="f705e-107">Quando un utente tenta di effettuare un acquisto in modalità self-service per un prodotto bloccato, può inviare una richiesta di licenza all'amministratore. Quando effettua una richiesta, può aggiungere i nomi di altri utenti che necessitano anche di licenze per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="f705e-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="f705e-108">Se si bloccano gli utenti dall'effettuare acquisti self-service, Microsoft non invia loro messaggi di posta elettronica di marketing.</span><span class="sxs-lookup"><span data-stu-id="f705e-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="f705e-109">Inoltre, se usano una versione di valutazione di un prodotto, non visualizzano istruzioni per acquistarlo.</span><span class="sxs-lookup"><span data-stu-id="f705e-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="f705e-110">Per ulteriori informazioni, vedere [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span><span class="sxs-lookup"><span data-stu-id="f705e-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="f705e-111">Per visualizzare e gestire le richieste di licenza, l'amministratore usa la **scheda Richieste** nella **pagina Licenze.**</span><span class="sxs-lookup"><span data-stu-id="f705e-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="f705e-112">L'elenco mostra il nome del prodotto richiesto, il nome della persona che richiede una licenza, la data richiesta e lo stato della richiesta.</span><span class="sxs-lookup"><span data-stu-id="f705e-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="f705e-113">Gli amministratori possono filtrare l'elenco per visualizzare le richieste in sospeso o completate.</span><span class="sxs-lookup"><span data-stu-id="f705e-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="f705e-114">Le richieste vengono mantenute per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f705e-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f705e-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f705e-115">Before you begin</span></span>

<span data-ttu-id="f705e-116">Per eseguire le attività in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f705e-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="f705e-117">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f705e-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="f705e-118">Usare il proprio processo di richiesta</span><span class="sxs-lookup"><span data-stu-id="f705e-118">Use your own request process</span></span>

<span data-ttu-id="f705e-119">Se l'organizzazione dispone di un proprio processo di richiesta, è possibile utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="f705e-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="f705e-120">Si crea un messaggio che viene visualizzato agli utenti quando richiedono una licenza.</span><span class="sxs-lookup"><span data-stu-id="f705e-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f705e-121">Se si utilizza il proprio processo di richiesta, nella **scheda** Richieste non viene visualizzata alcuna richiesta. Le richieste esistenti prima di aggiungere il messaggio continuano a essere visualizzate fino a quando non vengono approvate o rifiutate.</span><span class="sxs-lookup"><span data-stu-id="f705e-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="f705e-122">Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione, quindi selezionare la **scheda** Richieste.</span><span class="sxs-lookup"><span data-stu-id="f705e-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="f705e-123">Selezionare **Usa invece il processo di richiesta esistente.**</span><span class="sxs-lookup"><span data-stu-id="f705e-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="f705e-124">Nella casella Messaggio del  riquadro destro digitare il messaggio che si desidera visualizzare quando gli utenti richiedono una licenza.</span><span class="sxs-lookup"><span data-stu-id="f705e-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="f705e-125">Se si desidera includere anche un collegamento ai criteri dell'organizzazione o ad altra documentazione, immettere l'URL nella casella di testo Collegamento alla **documentazione (facoltativo).**</span><span class="sxs-lookup"><span data-stu-id="f705e-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="f705e-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f705e-126">Select **Save**.</span></span>

<span data-ttu-id="f705e-127">Quando si torna **all'elenco Richieste,** viene visualizzato il messaggio **You're using your own license request process**.</span><span class="sxs-lookup"><span data-stu-id="f705e-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="f705e-128">Per apportare modifiche al messaggio inviato agli utenti, selezionare **Usa il processo di richiesta esistente.**</span><span class="sxs-lookup"><span data-stu-id="f705e-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="f705e-129">Interrompere l'uso del proprio processo di richiesta</span><span class="sxs-lookup"><span data-stu-id="f705e-129">Stop using your own request process</span></span>

1. <span data-ttu-id="f705e-130">Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione, quindi selezionare la **scheda** Richieste.</span><span class="sxs-lookup"><span data-stu-id="f705e-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="f705e-131">Selezionare **Usa invece il processo di richiesta esistente.**</span><span class="sxs-lookup"><span data-stu-id="f705e-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="f705e-132">Nel riquadro destro deselezionare la casella di controllo Usa processo di richiesta **dell'organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="f705e-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="f705e-133">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f705e-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="f705e-134">Approvare o rifiutare una richiesta di licenza</span><span class="sxs-lookup"><span data-stu-id="f705e-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="f705e-135">Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione, quindi selezionare la **scheda** Richieste.</span><span class="sxs-lookup"><span data-stu-id="f705e-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="f705e-136">Selezionare la riga contenente la richiesta che si desidera esaminare.</span><span class="sxs-lookup"><span data-stu-id="f705e-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="f705e-137">Il riquadro destro mostra i dettagli sugli utenti che desiderano licenze per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="f705e-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="f705e-138">Per rifiutare **l'intera** richiesta, selezionare Non approvare e nella finestra di dialogo selezionare **Non approvare**.</span><span class="sxs-lookup"><span data-stu-id="f705e-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="f705e-139">Per rifiutare alcuni utenti per la richiesta, ma approvarli, selezionare la X in base al nome degli utenti che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="f705e-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="f705e-140">I nomi vengono spostati in **Non assegnare a questi utenti**.</span><span class="sxs-lookup"><span data-stu-id="f705e-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="f705e-141">Se si dispone di più di un prodotto, in Selezionare un **prodotto** selezionare quello che si desidera utilizzare per assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="f705e-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="f705e-142">Per negare agli utenti l'accesso a determinate app e servizi, espandi Attiva o disattiva app e **servizi,** quindi deseleziona le caselle di controllo per quelle che vuoi escludere.</span><span class="sxs-lookup"><span data-stu-id="f705e-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="f705e-143">Nella parte inferiore del riquadro digitare un messaggio facoltativo nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="f705e-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="f705e-144">Al termine, selezionare **Approva**.</span><span class="sxs-lookup"><span data-stu-id="f705e-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="f705e-145">Il riquadro destro mostra i dettagli della richiesta.</span><span class="sxs-lookup"><span data-stu-id="f705e-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="f705e-146">Chiudere il riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="f705e-146">Close the right pane.</span></span>
    <span data-ttu-id="f705e-147">Gli utenti ricevono un messaggio di posta elettronica che indica che la richiesta è stata approvata o rifiutata.</span><span class="sxs-lookup"><span data-stu-id="f705e-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="f705e-148">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="f705e-148">Related content</span></span>

<span data-ttu-id="f705e-149">[Assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="f705e-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="f705e-150">[Spostare gli utenti in un abbonamento diverso](../subscriptions/move-users-different-subscription.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="f705e-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="f705e-151">[Acquistare o rimuovere licenze di sottoscrizione](buy-licenses.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="f705e-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>
