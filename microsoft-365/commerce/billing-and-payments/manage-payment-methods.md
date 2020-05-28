---
title: Gestire metodi di pagamento
f1.keywords:
- CSH
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
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Informazioni su come gestire i metodi di pagamento nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 0320f71180a5c2c127217ebf01854943409e6386
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403679"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="54b57-103">Gestire metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="54b57-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="54b57-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="54b57-104">The admin center is changing.</span></span> <span data-ttu-id="54b57-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="54b57-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="54b57-106">Quando si acquistano prodotti o servizi aziendali da Microsoft, è possibile utilizzare un metodo di pagamento esistente oppure aggiungerne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="54b57-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="54b57-107">È possibile utilizzare una carta di credito o di debito o un conto corrente bancario per pagare le operazioni acquistate.</span><span class="sxs-lookup"><span data-stu-id="54b57-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="54b57-108">Se l'account aziendale ha un profilo di fatturazione e si è proprietari del profilo di fatturazione o collaboratore del profilo di fatturazione, è possibile utilizzare il profilo di fatturazione che è stato sottoposto a pagamento tramite carta di credito o fattura per effettuare acquisti o pagare le bollette.</span><span class="sxs-lookup"><span data-stu-id="54b57-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="54b57-109">Se si è un responsabile fatture fatturazione, è possibile utilizzare un profilo di fatturazione solo per pagare le bollette.</span><span class="sxs-lookup"><span data-stu-id="54b57-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="54b57-110">Per ulteriori informazioni sui ruoli e i profili di fatturazione, vedere [Manage Billing Profiles](manage-billing-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="54b57-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="54b57-111">Se l'account aziendale non dispone di un profilo di fatturazione, qualsiasi amministratore globale o di fatturazione può gestire e utilizzare qualsiasi account bancario aggiunto all'account aziendale.</span><span class="sxs-lookup"><span data-stu-id="54b57-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="54b57-112">Tuttavia, è possibile gestire o utilizzare solo carte di credito aggiunte.</span><span class="sxs-lookup"><span data-stu-id="54b57-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="54b57-113">La possibilità di pagare con un conto corrente bancario non è disponibile in alcuni paesi o aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="54b57-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="54b57-114">È necessario utilizzare un metodo di pagamento emesso dallo stesso paese del tenant.</span><span class="sxs-lookup"><span data-stu-id="54b57-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="54b57-115">Aggiungere una modalità di pagamento</span><span class="sxs-lookup"><span data-stu-id="54b57-115">Add a payment method</span></span>

<span data-ttu-id="54b57-116">L'aggiunta di un metodo di pagamento non associa gli abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="54b57-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="54b57-117">Per assegnare una singola sottoscrizione al metodo di pagamento, vedere [modificare un metodo di pagamento per una singola sottoscrizione](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="54b57-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="54b57-118">Per sostituire tutte le sottoscrizioni che utilizzano un altro metodo di pagamento con quello nuovo, vedere [Replace a Payment Method](#replace-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="54b57-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="54b57-119">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="54b57-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="54b57-120">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="54b57-121">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="54b57-122">Selezionare **Aggiungere una modalità di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="54b57-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="54b57-123">Nella pagina **Modalità di pagamento** scegliere una modalità di pagamento dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="54b57-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="54b57-124">Immettere le informazioni per la nuova scheda o il conto corrente bancario, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="54b57-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="54b57-125">Aggiornare i dettagli della modalità di pagamento</span><span class="sxs-lookup"><span data-stu-id="54b57-125">Update payment method details</span></span>

<span data-ttu-id="54b57-126">È possibile modificare il nome sulla carta di credito o di debito, l'indirizzo di fatturazione o la data di scadenza di un metodo di pagamento esistente.</span><span class="sxs-lookup"><span data-stu-id="54b57-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="54b57-127">Tuttavia, non è possibile modificare il numero di carta o di account.</span><span class="sxs-lookup"><span data-stu-id="54b57-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="54b57-128">Se il numero dell'account è stato modificato, [sostituirlo con un metodo di pagamento diverso](#replace-a-payment-method), quindi [eliminare quello precedente](#delete-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="54b57-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="54b57-129">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="54b57-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="54b57-130">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="54b57-131">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="54b57-132">Selezionare la riga della modalità di pagamento da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="54b57-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="54b57-133">Nel riquadro destro, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="54b57-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="54b57-134">Aggiornare le informazioni sulla modalità di pagamento, inclusi il nome sulla carta di credito o di debito, l'indirizzo di fatturazione o la data di scadenza e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="54b57-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="54b57-135">Sostituire un metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="54b57-135">Replace a payment method</span></span>

<span data-ttu-id="54b57-136">Quando si sostituisce un metodo di pagamento, è necessario sostituirlo per tutte le sottoscrizioni e i profili di fatturazione che utilizzano lo stesso metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="54b57-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="54b57-137">La sostituzione di un metodo di pagamento non comporta l'eliminazione del metodo di pagamento esistente.</span><span class="sxs-lookup"><span data-stu-id="54b57-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="54b57-138">È ancora disponibile per la selezione e l'utilizzo di altri abbonamenti e profili di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="54b57-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="54b57-139">Per modificare il metodo di pagamento per una singola sottoscrizione, vedere [modificare un metodo di pagamento per una singola sottoscrizione](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="54b57-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="54b57-140">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="54b57-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="54b57-141">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="54b57-142">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="54b57-143">Selezionare la riga della modalità di pagamento da sostituire.</span><span class="sxs-lookup"><span data-stu-id="54b57-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="54b57-144">Nel riquadro destro sono elencati tutti i profili di fatturazione e i singoli abbonamenti che usano la modalità di pagamento selezionata.</span><span class="sxs-lookup"><span data-stu-id="54b57-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="54b57-145">Nel riquadro destro selezionare **Sostituisci metodo di pagamento per tutti gli articoli**.</span><span class="sxs-lookup"><span data-stu-id="54b57-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="54b57-146">Per usare una modalità di pagamento esistente, sceglierne una nell'elenco a discesa, quindi selezionare **Sostituisci**.</span><span class="sxs-lookup"><span data-stu-id="54b57-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="54b57-147">Se si hanno abbonamenti associati a un profilo di fatturazione, si può usare solo una carta di credito o di debito per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="54b57-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="54b57-148">Se nella pagina **Modalità di pagamento** sono elencati conti bancari, non sono disponibili per la selezione nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="54b57-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="54b57-149">Per aggiungere una nuova modalità di pagamento, selezionare **Aggiungi modalità di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="54b57-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="54b57-150">Nel riquadro **Aggiungi un metodo di pagamento** immetti le informazioni sull'account e scegli **Salva**.</span><span class="sxs-lookup"><span data-stu-id="54b57-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="54b57-151">È necessario usare una modalità di pagamento dello stesso paese/area geografica del tenant.</span><span class="sxs-lookup"><span data-stu-id="54b57-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="54b57-152">La nuova modalità di pagamento è già selezionata nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="54b57-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="54b57-153">Selezionare **Sostituisci**.</span><span class="sxs-lookup"><span data-stu-id="54b57-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="54b57-154">Modificare un metodo di pagamento per un singolo abbonamento</span><span class="sxs-lookup"><span data-stu-id="54b57-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="54b57-155">È possibile modificare il metodo di pagamento utilizzato per pagare un singolo abbonamento.</span><span class="sxs-lookup"><span data-stu-id="54b57-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="54b57-156">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="54b57-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="54b57-157">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > **I tuoi prodotti**.</span><span class="sxs-lookup"><span data-stu-id="54b57-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="54b57-158">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > **I tuoi prodotti**.</span><span class="sxs-lookup"><span data-stu-id="54b57-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="54b57-159">Nella scheda **abbonamenti** selezionare l'abbonamento che si desidera pagare con il metodo di pagamento alternativo.</span><span class="sxs-lookup"><span data-stu-id="54b57-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="54b57-160">In **fatturazione**, fare clic su **modifica**accanto al metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="54b57-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="54b57-161">Accanto al metodo di pagamento esistente, selezionare **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="54b57-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="54b57-162">Nell'elenco a discesa scegliere un metodo di pagamento alternativo oppure scegliere di aggiungere un metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="54b57-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="54b57-163">Se si aggiunge un metodo di pagamento, immettere la scheda o i dettagli dell'account, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="54b57-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="54b57-164">Verificare che il metodo di pagamento selezionato sia corretto, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="54b57-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="54b57-165">Eliminare un metodo di pagamento</span><span class="sxs-lookup"><span data-stu-id="54b57-165">Delete a payment method</span></span>

<span data-ttu-id="54b57-166">È possibile eliminare solo un metodo di pagamento che non è collegato a un abbonamento o a un profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="54b57-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="54b57-167">Questo vale per tutte le sottoscrizioni, indipendentemente dallo stato.</span><span class="sxs-lookup"><span data-stu-id="54b57-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="54b57-168">Eliminare un metodo di pagamento senza abbonamenti o profili di fatturazione associati</span><span class="sxs-lookup"><span data-stu-id="54b57-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="54b57-169">Se un metodo di pagamento non è associato ad alcun abbonamento o profilo di fatturazione, è possibile eliminarlo immediatamente.</span><span class="sxs-lookup"><span data-stu-id="54b57-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="54b57-170">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="54b57-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="54b57-171">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="54b57-172">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="54b57-173">Trovare il metodo di pagamento da eliminare, selezionare i tre punti, quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="54b57-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="54b57-174">Nella parte inferiore del riquadro destro fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="54b57-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="54b57-175">Eliminare un metodo di pagamento con abbonamenti o profili di fatturazione associati</span><span class="sxs-lookup"><span data-stu-id="54b57-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="54b57-176">Se un metodo di pagamento è collegato a qualsiasi sottoscrizione o profilo di fatturazione, sostituirlo con un metodo di pagamento esistente oppure aggiungerne uno nuovo, quindi eliminare il vecchio metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="54b57-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="54b57-177">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="54b57-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="54b57-178">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="54b57-179">Nell'interfaccia di amministrazione, accedere alla pagina dei metodi di pagamento per la **fatturazione** > **& pagamenti** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="54b57-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="54b57-180">Selezionare la riga per il metodo di pagamento da eliminare.</span><span class="sxs-lookup"><span data-stu-id="54b57-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="54b57-181">Nel riquadro destro sono elencate le sottoscrizioni esistenti che utilizzano il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="54b57-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="54b57-182">Nel riquadro a destra, selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="54b57-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="54b57-183">Per utilizzare un metodo di pagamento esistente, selezionarlo nell'elenco a discesa, selezionare **Avanti**, quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="54b57-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="54b57-184">Se si dispone di abbonamenti associati a un profilo di fatturazione, è possibile utilizzare solo una carta di credito per pagarli.</span><span class="sxs-lookup"><span data-stu-id="54b57-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="54b57-185">Se si dispone di account bancari elencati nella pagina **metodi di pagamento** , non sono disponibili per la scelta nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="54b57-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="54b57-186">Per aggiungere una nuova modalità di pagamento, selezionare **Aggiungi modalità di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="54b57-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="54b57-187">Scegliere il tipo di metodo di pagamento che si desidera aggiungere, immettere le informazioni dell'account e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="54b57-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="54b57-188">La nuova modalità di pagamento è già selezionata nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="54b57-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="54b57-189">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="54b57-189">Select **Next**.</span></span>

8. <span data-ttu-id="54b57-190">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="54b57-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="54b57-191">Risoluzione dei problemi relativi alle modalità di pagamento</span><span class="sxs-lookup"><span data-stu-id="54b57-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="54b57-192">**Problema**</span><span class="sxs-lookup"><span data-stu-id="54b57-192">**Issue**</span></span>|<span data-ttu-id="54b57-193">**Procedure per la risoluzione dei problemi**</span><span class="sxs-lookup"><span data-stu-id="54b57-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="54b57-194">**Viene visualizzato un messaggio di errore che indica che il browser è attualmente impostato per bloccare i cookie.**</span><span class="sxs-lookup"><span data-stu-id="54b57-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="54b57-195">Impostare il browser in modo da accettare i cookie di terze parti e riprovare.</span><span class="sxs-lookup"><span data-stu-id="54b57-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="54b57-196">**La carta di credito o di debito è stata rifiutata.**</span><span class="sxs-lookup"><span data-stu-id="54b57-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="54b57-197">Se si paga con carta di credito o di debito e la scheda viene rifiutata, viene visualizzato un messaggio di posta elettronica che indica che Microsoft non è stato in grado di elaborare il pagamento.</span><span class="sxs-lookup"><span data-stu-id="54b57-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="54b57-198">Verificare che il numero di carta dei dettagli della scheda &mdash; , la data di scadenza, il nome della scheda e l'indirizzo, inclusi la città, lo stato e il codice postale &mdash; vengano visualizzati esattamente come nella scheda e nell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="54b57-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="54b57-199">È possibile aggiornare le informazioni sulla scheda e inoltrare immediatamente il pagamento utilizzando il collegamento **Risolvi saldo** nella sezione **fatturazione** della pagina Dettagli sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="54b57-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="54b57-200">Per ulteriori informazioni, vedere [cosa succede se la carta di credito è stata rifiutata e il pagamento è scaduto?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span><span class="sxs-lookup"><span data-stu-id="54b57-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="54b57-201">Se si continua a visualizzare il messaggio "rifiutato", contattare la propria banca.</span><span class="sxs-lookup"><span data-stu-id="54b57-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="54b57-202">È possibile che la scheda non sia attiva.</span><span class="sxs-lookup"><span data-stu-id="54b57-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="54b57-203">Se la scheda è stata ricevuta di recente nella posta con una data di scadenza aggiornata, assicurarsi che sia attivata.</span><span class="sxs-lookup"><span data-stu-id="54b57-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="54b57-204">La banca può anche indicare se la scheda non è stata approvata per transazioni online, internazionali o ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="54b57-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="54b57-205">**Si desidera aggiornare una scheda o un numero di conto corrente bancario.**</span><span class="sxs-lookup"><span data-stu-id="54b57-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="54b57-206">Non è possibile modificare il numero di carta o di account su un metodo di pagamento esistente.</span><span class="sxs-lookup"><span data-stu-id="54b57-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="54b57-207">Se la scheda o il numero di account è stato modificato, [sostituirlo con un metodo di pagamento diverso](#replace-a-payment-method), che sposta tutti gli abbonamenti attivi dal metodo di pagamento a quello nuovo, quindi [eliminare il vecchio metodo di pagamento](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span><span class="sxs-lookup"><span data-stu-id="54b57-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="54b57-208">**Ho solo una carta o un conto corrente bancario sul mio account e lo si desidera rimuovere.**</span><span class="sxs-lookup"><span data-stu-id="54b57-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="54b57-209">Se si dispone di un solo metodo di pagamento, è necessario [sostituirlo con un nuovo metodo di pagamento prima di](#replace-a-payment-method) eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="54b57-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="54b57-210">**Non è possibile aggiungere la scheda o il conto corrente bancario.**</span><span class="sxs-lookup"><span data-stu-id="54b57-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="54b57-211">È necessario utilizzare un metodo di pagamento emesso dallo stesso paese del tenant.</span><span class="sxs-lookup"><span data-stu-id="54b57-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="54b57-212">In caso di problemi nell'immissione delle informazioni sulla carta o sul conto corrente bancario, è possibile [contattare il supporto tecnico](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="54b57-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="54b57-213">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="54b57-213">Related articles</span></span>

[<span data-ttu-id="54b57-214">Pagare l'abbonamento per le aziende</span><span class="sxs-lookup"><span data-stu-id="54b57-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="54b57-215">Gestire profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="54b57-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="54b57-216">Modificare la frequenza di pagamento</span><span class="sxs-lookup"><span data-stu-id="54b57-216">Change your payment frequency</span></span>](change-payment-frequency.md)