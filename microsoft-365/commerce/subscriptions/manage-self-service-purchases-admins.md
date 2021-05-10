---
title: Gestire gli acquisti in modalità self-service (amministratori)
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce
search.appverid:
- MET150
description: Gli amministratori possono imparare a gestire gli acquisti self-service effettuati dagli utenti nell'organizzazione.
ms.openlocfilehash: 5378d14affd074bfad356fea4bb2adbd6ca104dd
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293572"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="adfd1-103">Gestire acquisti in modalità self-service (amministratore)</span><span class="sxs-lookup"><span data-stu-id="adfd1-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="adfd1-104">Gli amministratori possono visualizzare gli acquisti in modalità self-service effettuati da persone dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="adfd1-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="adfd1-105">Vengono visualizzati il nome del prodotto, il nome dell'acquirente, le sottoscrizioni acquistate, la data di scadenza, il prezzo di acquisto e gli utenti assegnati per ogni acquisto self-service.</span><span class="sxs-lookup"><span data-stu-id="adfd1-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="adfd1-106">Se richiesto dall'organizzazione, è possibile disattivare gli acquisti self-service in base al prodotto tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="adfd1-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="adfd1-107">Si dispone degli stessi criteri di gestione dei dati e di accesso sui prodotti acquistati tramite acquisto self-service o centralmente.</span><span class="sxs-lookup"><span data-stu-id="adfd1-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="adfd1-108">È inoltre possibile controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="adfd1-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="adfd1-109">Per ulteriori informazioni, vedere [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="adfd1-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="adfd1-110">Visualizzare le sottoscrizioni self-service</span><span class="sxs-lookup"><span data-stu-id="adfd1-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="adfd1-111">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="adfd1-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="adfd1-112">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="adfd1-112">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="adfd1-113">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="adfd1-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="adfd1-114">Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Self-service**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="adfd1-115">Per visualizzare altri dettagli su una sottoscrizione, selezionarne uno dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="adfd1-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="adfd1-116">Visualizzare chi dispone di licenze per una sottoscrizione di acquisto self-service</span><span class="sxs-lookup"><span data-stu-id="adfd1-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="adfd1-117">Gli amministratori non possono assegnare o annullare l'assegnazione di licenze per un abbonamento acquistato in modalità self-service da un utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="adfd1-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="adfd1-118">È possibile [assumere il controllo di un abbonamento acquistato in modalità self-service](#take-over-a-self-service-purchase-subscription) e quindi assegnare licenze o annullarne l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="adfd1-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="adfd1-119">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="adfd1-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="adfd1-120">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="adfd1-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="adfd1-121">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="adfd1-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="adfd1-122">Seleziona l'icona del filtro, quindi scegli **Self-service.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="adfd1-123">Selezionare un prodotto per visualizzare le licenze assegnate agli utenti.</span><span class="sxs-lookup"><span data-stu-id="adfd1-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="adfd1-124">Se sono presenti più acquisti per un prodotto, tale prodotto viene elencato una sola volta e nella colonna **Quantità** disponibile viene visualizzato il totale di tutte le sottoscrizioni acquistate per tale prodotto.</span><span class="sxs-lookup"><span data-stu-id="adfd1-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="adfd1-125">**L'elenco** Utenti è raggruppato in base ai nomi delle persone che hanno effettuato acquisti self-service.</span><span class="sxs-lookup"><span data-stu-id="adfd1-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="adfd1-126">Per esportare un elenco di utenti con licenze per queste sottoscrizioni, scegliere le sottoscrizioni che si desidera esportare, quindi scegliere **Esporta utenti**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="adfd1-127">Disabilitare o abilitare gli acquisti in modalità self-service</span><span class="sxs-lookup"><span data-stu-id="adfd1-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="adfd1-128">È possibile disabilitare o abilitare gli acquisti in modalità self-service per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="adfd1-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="adfd1-129">Il **modulo MSCommerce** PowerShell include un valore del parametro **PolicyID** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service e per quali prodotti.</span><span class="sxs-lookup"><span data-stu-id="adfd1-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="adfd1-130">È possibile utilizzare il **modulo ms-Commerce** PowerShell per:</span><span class="sxs-lookup"><span data-stu-id="adfd1-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="adfd1-131">Visualizzare lo stato predefinito del **valore del parametro AllowSelfServicePurchase,** indipendentemente dal fatto che sia abilitato o disabilitato dal prodotto</span><span class="sxs-lookup"><span data-stu-id="adfd1-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="adfd1-132">Visualizzare un elenco dei prodotti applicabili e se l'acquisto in self-service è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="adfd1-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="adfd1-133">Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarla o disabilitarla</span><span class="sxs-lookup"><span data-stu-id="adfd1-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="adfd1-134">Per ulteriori informazioni, vedere [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="adfd1-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="adfd1-135">Centralizzare le licenze con un singolo abbonamento</span><span class="sxs-lookup"><span data-stu-id="adfd1-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="adfd1-136">È possibile assegnare licenze esistenti o acquistare abbonamenti aggiuntivi tramite contratti esistenti per gli utenti assegnati agli acquisti self-service.</span><span class="sxs-lookup"><span data-stu-id="adfd1-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="adfd1-137">Dopo aver assegnato queste licenze acquistate centralmente, è possibile richiedere agli acquirenti di annullare le sottoscrizioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="adfd1-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="adfd1-138">Nell'interfaccia di amministrazione passare alla **pagina Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Acquisto servizi.</a></span><span class="sxs-lookup"><span data-stu-id="adfd1-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="adfd1-139"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Fatturazione** > **Acquisto servizi.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="adfd1-140"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Fatturazione** > **Acquisto servizi.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="adfd1-141">Trova e scegli il prodotto che vuoi acquistare, quindi scegli **Acquista**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="adfd1-142">Completa i passaggi rimanenti per completare l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="adfd1-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="adfd1-143">Seguire i passaggi descritti in Visualizzare chi ha licenze per una sottoscrizione acquistata [in modalità self-service](#view-who-has-licenses-for-a-self-service-purchase-subscription) per esportare un elenco di utenti a cui fare riferimento nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="adfd1-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="adfd1-144">Assegnare licenze a tutti gli utenti che hanno una licenza nell'altro abbonamento.</span><span class="sxs-lookup"><span data-stu-id="adfd1-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="adfd1-145">Per la procedura completa, vedere [Assegnare licenze agli utenti.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="adfd1-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="adfd1-146">Contattare la persona che ha acquistato la sottoscrizione di acquisto self-service e chiedere di [annullarla.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="adfd1-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="adfd1-147">Assumere una sottoscrizione di acquisto self-service</span><span class="sxs-lookup"><span data-stu-id="adfd1-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="adfd1-148">È possibile assumere una sottoscrizione di acquisto self-service effettuata da un utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="adfd1-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="adfd1-149">Quando si acquista una sottoscrizione self-service, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="adfd1-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="adfd1-150">Spostare gli utenti in un'altra sottoscrizione e annullare la sottoscrizione originale.</span><span class="sxs-lookup"><span data-stu-id="adfd1-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="adfd1-151">Annullare la sottoscrizione di acquisto self-service e rimuovere le licenze dagli utenti assegnati.</span><span class="sxs-lookup"><span data-stu-id="adfd1-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="adfd1-152">Trasferire gli utenti a un abbonamento diverso</span><span class="sxs-lookup"><span data-stu-id="adfd1-152">Move users to a different subscription</span></span>

<span data-ttu-id="adfd1-153">Quando si spostano gli utenti in un abbonamento diverso, la sottoscrizione precedente viene automaticamente annullata.</span><span class="sxs-lookup"><span data-stu-id="adfd1-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="adfd1-154">L'utente che ha acquistato in origine la sottoscrizione di acquisto self-service riceve un messaggio di posta elettronica che indica che l'abbonamento è stato annullato.</span><span class="sxs-lookup"><span data-stu-id="adfd1-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="adfd1-155">È necessario disporre di una licenza disponibile per ogni utente in cui si sta spostando l'abbonamento in cui si stanno spostando gli utenti.</span><span class="sxs-lookup"><span data-stu-id="adfd1-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="adfd1-156">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="adfd1-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="adfd1-157"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Fatturazione** > **prodotti.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="adfd1-158"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Fatturazione** > **prodotti.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="adfd1-159">Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Self-service**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="adfd1-160">Selezionare l'abbonamento che si desidera assumere.</span><span class="sxs-lookup"><span data-stu-id="adfd1-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="adfd1-161">Nella sezione Sottoscrizioni e  impostazioni della pagina dei dettagli dell'abbonamento selezionare Prendi **il controllo della sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="adfd1-162">Nel riquadro destro selezionare **Sposta utenti**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="adfd1-163">Selezionare il prodotto in cui si desidera spostare gli utenti, quindi selezionare **Sposta utenti**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="adfd1-164">Nella casella **Sposta utenti in** selezionare Sposta **utenti**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="adfd1-165">Il processo di spostamento potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="adfd1-165">The move process might take several minutes.</span></span> <span data-ttu-id="adfd1-166">Non chiudere il browser durante l'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="adfd1-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="adfd1-167">Al termine del processo di spostamento, chiudere il **riquadro Sposta completato.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="adfd1-168">Nella pagina dei dettagli della sottoscrizione, lo **stato della** sottoscrizione per la sottoscrizione acquistata in self-service viene visualizzato come **Eliminato.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="adfd1-169">Annullare una sottoscrizione di acquisto self-service</span><span class="sxs-lookup"><span data-stu-id="adfd1-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="adfd1-170">Quando si sceglie di annullare una sottoscrizione di acquisto self-service, gli utenti con licenze perdono l'accesso al prodotto.</span><span class="sxs-lookup"><span data-stu-id="adfd1-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="adfd1-171">L'utente che ha acquistato in origine la sottoscrizione di acquisto self-service riceve un messaggio di posta elettronica che indica che l'abbonamento è stato annullato.</span><span class="sxs-lookup"><span data-stu-id="adfd1-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="adfd1-172">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="adfd1-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="adfd1-173"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Fatturazione** > **prodotti.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="adfd1-174"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Fatturazione** > **prodotti.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="adfd1-175">Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Self-service**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="adfd1-176">Selezionare l'abbonamento che si vuole annullare.</span><span class="sxs-lookup"><span data-stu-id="adfd1-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="adfd1-177">Nella sezione Sottoscrizioni e  impostazioni della pagina dei dettagli dell'abbonamento selezionare Prendi **il controllo della sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="adfd1-178">Nel riquadro destro selezionare **Annulla sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="adfd1-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="adfd1-179">Selezionare un motivo per l'annullamento dall'elenco a discesa, quindi selezionare **Annulla sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="adfd1-180">Nella casella **Si è certi di voler annullare?** selezionare Annulla **sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="adfd1-181">Chiudere il riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="adfd1-181">Close the right pane.</span></span>
9. <span data-ttu-id="adfd1-182">Nella pagina dei dettagli della sottoscrizione lo **stato della sottoscrizione** viene visualizzato come **Eliminato.**</span><span class="sxs-lookup"><span data-stu-id="adfd1-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="adfd1-183">Hai bisogno di assistenza?</span><span class="sxs-lookup"><span data-stu-id="adfd1-183">Need help?</span></span> <span data-ttu-id="adfd1-184">Contattaci.</span><span class="sxs-lookup"><span data-stu-id="adfd1-184">Contact us.</span></span>

<span data-ttu-id="adfd1-185">Per domande frequenti sugli acquisti self-service, vedere Domande frequenti [sugli acquisti in self-service.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="adfd1-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="adfd1-186">Se hai domande o hai bisogno di assistenza per gli acquisti self-service, [contatta il supporto](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="adfd1-186">If you have questions or need help with self-service purchases, [contact support](../../business-video/get-help-support.md).</span></span>