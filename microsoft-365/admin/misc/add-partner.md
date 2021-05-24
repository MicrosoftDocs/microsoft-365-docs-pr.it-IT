---
title: Aggiungere, modificare o rimuovere un partner con il ruolo di consulente dell'abbonamento
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
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: Aggiungere un partner di record al momento dell'Microsoft 365, modificare il partner o eliminare un partner da una sottoscrizione.
ms.openlocfilehash: e21c324bc84e360b80deae2abeec610e73834819
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624526"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="79394-103">Aggiungere, modificare o rimuovere un partner con il ruolo di consulente dell'abbonamento</span><span class="sxs-lookup"><span data-stu-id="79394-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="79394-104">Questo articolo si applica Office 365 gestito da 21Vianet in Cina.</span><span class="sxs-lookup"><span data-stu-id="79394-104">This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="79394-105">È per le organizzazioni che desiderano consentire a un partner 21Vianet di amministrare la Office 365 per loro.</span><span class="sxs-lookup"><span data-stu-id="79394-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="79394-106">Un partner Microsoft autorizzato che opera come consulente dell'abbonamento mette a disposizione la sua esperienza in materia di vendite, supporto e assistenza tecnica per aiutare a configurare e gestire l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="79394-106">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="79394-107">È possibile aggiungere un partner consulente della sottoscrizione come partner del record quando si acquista Microsoft 365 o in un altro momento.</span><span class="sxs-lookup"><span data-stu-id="79394-107">You can add a subscription advisor partner as a partner of record when you purchase Microsoft 365 or at another time.</span></span> <span data-ttu-id="79394-108">Se attualmente non si lavora con un partner, è anche possibile trovarlo nel sito [Web Microsoft Pinpoint.](https://pinpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="79394-108">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="79394-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="79394-109">Before you begin</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="79394-110">Il partner scelto dipende dal servizi Microsoft utilizzato e dal paese o dall'area geografica in cui verranno utilizzati tali servizi.</span><span class="sxs-lookup"><span data-stu-id="79394-110">The partner you choose depends on the Microsoft services you use and the country or region where you'll use those services.</span></span> <span data-ttu-id="79394-111">Se si sta aggiungendo un partner o cambiando il partner dell'abbonamento, per prima cosa è necessario ottenere il suo ID partner Microsoft, chiedendo al partner stesso.</span><span class="sxs-lookup"><span data-stu-id="79394-111">If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="79394-112">Un partner Microsoft autorizzato che opera come consulente dell'abbonamento mette a disposizione la sua esperienza in materia di vendite, supporto e assistenza tecnica per aiutare a configurare e gestire l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="79394-112">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="79394-113">È possibile aggiungere un partner con il ruolo di consulente dell'abbonamento come Partner of Record quando si acquista Office 365 o in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="79394-113">You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time.</span></span> <span data-ttu-id="79394-114">Se attualmente non si lavora con un partner, è anche possibile trovarlo nel sito [Web Microsoft Pinpoint.](https://pinpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="79394-114">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="79394-p105">Il partner scelto dipende dai servizi di Office 365 usati e dal paese o dall'area geografica in cui questi saranno usati. Se si sta aggiungendo un partner o cambiando il partner dell'abbonamento, per prima cosa è necessario ottenere il suo ID partner Microsoft, chiedendo al partner stesso.</span><span class="sxs-lookup"><span data-stu-id="79394-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="79394-117">In quanto amministratore di Office 365, è possibile creare o modificare utenti, reimpostare le password utente, gestire le licenze utente, gestire i domini e assegnare autorizzazioni di amministratore ad altri utenti dell'organizzazione, tra le altre cose.</span><span class="sxs-lookup"><span data-stu-id="79394-117">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="79394-118">Tuttavia, se si desidera che altre persone esee possano eseguire queste attività amministrative, è possibile delegare questo ruolo a un partner autorizzato di 21Vianet creando una relazione partner.</span><span class="sxs-lookup"><span data-stu-id="79394-118">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="79394-119">Aggiungere un partner al momento dell'acquisto</span><span class="sxs-lookup"><span data-stu-id="79394-119">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="79394-120">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Acquisto servizi.</a></span><span class="sxs-lookup"><span data-stu-id="79394-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="79394-121">Selezionare il prodotto che si desidera acquistare e quindi selezionare **Acquista**.</span><span class="sxs-lookup"><span data-stu-id="79394-121">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="79394-122">Per aggiungere un nuovo partner, espandere **Serve assistenza per l'ordine e** selezionare Ottieni assistenza da un partner **Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="79394-122">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="79394-123">Seguire i passaggi nella pagina dei provider per cercare o ottenere una corrispondenza con un partner.</span><span class="sxs-lookup"><span data-stu-id="79394-123">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="79394-124">Se si dispone già di un partner, nel secondo passaggio della procedura guidata di estrazione, nel riquadro destro, in Informazioni partner, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79394-124">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="79394-p107">Immettere l'ID del partner Microsoft da aggiungere, che è possibile ottenere richiedendolo al partner stesso.</span><span class="sxs-lookup"><span data-stu-id="79394-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="79394-127">Completare la procedura guidata per terminare l'acquisto degli abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="79394-127">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="79394-128">Aggiungere un partner al momento dell'acquisto</span><span class="sxs-lookup"><span data-stu-id="79394-128">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="79394-129">[Nell'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041)passare alla pagina **Fatturazione** \> **Acquisto servizi.**</span><span class="sxs-lookup"><span data-stu-id="79394-129">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
2. <span data-ttu-id="79394-130">Selezionare il prodotto che si desidera acquistare e quindi selezionare **Acquista**.</span><span class="sxs-lookup"><span data-stu-id="79394-130">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="79394-131">Per aggiungere un nuovo partner, espandere **Serve assistenza per l'ordine e** selezionare Ottieni assistenza da un partner **Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="79394-131">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="79394-132">Seguire i passaggi nella pagina dei provider per cercare o ottenere una corrispondenza con un partner.</span><span class="sxs-lookup"><span data-stu-id="79394-132">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="79394-133">Se si dispone già di un partner, nel secondo passaggio della procedura guidata di estrazione, nel riquadro destro, in Informazioni partner, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79394-133">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="79394-p108">Immettere l'ID del partner Microsoft da aggiungere, che è possibile ottenere richiedendolo al partner stesso.</span><span class="sxs-lookup"><span data-stu-id="79394-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="79394-136">Completare la procedura guidata per terminare l'acquisto degli abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="79394-136">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="79394-137">Aggiunta di un partner a una sottoscrizione esistente</span><span class="sxs-lookup"><span data-stu-id="79394-137">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79394-138">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="79394-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="79394-139">Nella scheda **Prodotti** selezionare l'abbonamento che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="79394-139">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="79394-140">Nella pagina dei dettagli della sottoscrizione, in **Informazioni partner,** digitare l'ID **di rete del partner.**</span><span class="sxs-lookup"><span data-stu-id="79394-140">On the subscription details page, under **Partner information**, type the **Partner Network ID**.</span></span> <span data-ttu-id="79394-141">Puoi ottenere l'ID di Microsoft Partner Network del partner chiedendolo al partner.</span><span class="sxs-lookup"><span data-stu-id="79394-141">You can get the partner's Microsoft Partner Network ID by asking the partner for it.</span></span>
4. <span data-ttu-id="79394-142">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79394-142">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79394-143">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="79394-143">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="79394-144">Se si dispone di più sottoscrizioni, selezionare la sottoscrizione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="79394-144">If you have more than one subscription, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="79394-145">A destra, sotto il costo della sottoscrizione, selezionare i tre punti (altre azioni) > **Aggiungi partner di record**.</span><span class="sxs-lookup"><span data-stu-id="79394-145">On the right, under the subscription cost, select the three dots (more actions) > **Add partner of record**.</span></span>
4. <span data-ttu-id="79394-p110">Immettere l'ID del partner Microsoft da aggiungere, selezionare **Controlla ID** e quindi **Invia**. L'ID del partner Microsoft può essere richiesto al partner stesso.</span><span class="sxs-lookup"><span data-stu-id="79394-p110">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
5. <span data-ttu-id="79394-148">L'ID del partner è visualizzato nella pagina **Abbonamenti**.</span><span class="sxs-lookup"><span data-stu-id="79394-148">The partner ID displays on the **Subscriptions** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="79394-149">Questo processo viene avviato dal partner autorizzato.</span><span class="sxs-lookup"><span data-stu-id="79394-149">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="79394-150">Il partner invia un messaggio di posta elettronica per chiedere se si desidera concedere loro l'autorizzazione ad agire come partner del record.</span><span class="sxs-lookup"><span data-stu-id="79394-150">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span>
  
<span data-ttu-id="79394-151">Per accettare questa offerta</span><span class="sxs-lookup"><span data-stu-id="79394-151">To accept this offer</span></span>
  
1. <span data-ttu-id="79394-152">Leggere i termini del partner nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="79394-152">Read the partner's terms in the email.</span></span>
2. <span data-ttu-id="79394-153">Per autorizzare il contratto, selezionare il collegamento, che passa a una pagina di autorizzazione in Office 365.</span><span class="sxs-lookup"><span data-stu-id="79394-153">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
3. <span data-ttu-id="79394-154">In **Relazioni con** i partner seleziona **Sì** per autorizzare il partner a essere l'amministratore delegato e quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="79394-154">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
4. <span data-ttu-id="79394-155">Se l'offerta per la relazione con i partner è stata fornita con una sottoscrizione di valutazione o un'offerta di acquisto, creare l'account di valutazione o di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="79394-155">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>

::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="79394-156">Cambiare partner per un abbonamento</span><span class="sxs-lookup"><span data-stu-id="79394-156">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79394-157">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="79394-157">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="79394-158">Nella pagina dei dettagli delle sottoscrizioni, in **Informazioni partner,** selezionare **Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="79394-158">On the subscriptions details page, under **Partner information**, select **Remove**.</span></span>
3. <span data-ttu-id="79394-159">Digitare **l'ID di Microsoft Partner Network** per il nuovo partner.</span><span class="sxs-lookup"><span data-stu-id="79394-159">Type the **Microsoft Partner Network ID** for the new partner.</span></span> <span data-ttu-id="79394-160">Per ottenere l'ID del partner Microsoft, richiederlo al partner stesso.</span><span class="sxs-lookup"><span data-stu-id="79394-160">You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
4. <span data-ttu-id="79394-161">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="79394-161">Select **Add**.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79394-162">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="79394-162">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="79394-163">Se si dispone di più sottoscrizioni, selezionare il nome della sottoscrizione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="79394-163">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="79394-164">In **ID partner** selezionare **Modifica Partner of Record**.</span><span class="sxs-lookup"><span data-stu-id="79394-164">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="79394-p113">Immettere l'ID del nuovo partner Microsoft da aggiungere, selezionare **Controlla ID** e quindi **Invia**. L'ID del partner Microsoft può essere richiesto al partner stesso.</span><span class="sxs-lookup"><span data-stu-id="79394-p113">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79394-167">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="79394-167">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="79394-168">Se si dispone di più sottoscrizioni, selezionare il nome della sottoscrizione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="79394-168">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="79394-169">In **ID partner** selezionare **Modifica Partner of Record**.</span><span class="sxs-lookup"><span data-stu-id="79394-169">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="79394-p114">Immettere l'ID del nuovo partner Microsoft da aggiungere, selezionare **Controlla ID** e quindi **Invia**. L'ID del partner Microsoft può essere richiesto al partner stesso.</span><span class="sxs-lookup"><span data-stu-id="79394-p114">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

## <a name="view-your-partner-relationships"></a><span data-ttu-id="79394-172">Visualizzare le relazioni con i partner</span><span class="sxs-lookup"><span data-stu-id="79394-172">View your partner relationships</span></span>

- <span data-ttu-id="79394-173">Nell'interfaccia di amministrazione passare alla **pagina** Impostazioni  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">relazioni partner.</a></span><span class="sxs-lookup"><span data-stu-id="79394-173">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="79394-174">I partner sono elencati in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="79394-174">Your partners are listed on this page.</span></span>

  <span data-ttu-id="79394-175">Se non si dispone di un partner, verrà visualizzato il messaggio "Non c'è niente qui".</span><span class="sxs-lookup"><span data-stu-id="79394-175">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="79394-176">Eliminare un partner da un abbonamento</span><span class="sxs-lookup"><span data-stu-id="79394-176">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="79394-177">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="79394-177">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="79394-178">Nella scheda **Prodotti** selezionare l'abbonamento che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="79394-178">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="79394-179">Nella pagina dei dettagli della sottoscrizione, in **Informazioni partner,** selezionare **Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="79394-179">On the subscription details page, under **Partner information**, select **Remove**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="79394-180">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="79394-180">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="79394-181">Se si dispone di più sottoscrizioni, selezionare il nome della sottoscrizione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="79394-181">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="79394-182">In **ID partner** selezionare **Modifica Partner of Record**.</span><span class="sxs-lookup"><span data-stu-id="79394-182">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="79394-183">Nella pagina **Informazioni partner** deselezionare la casella **ID partner** e fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="79394-183">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="79394-184">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="79394-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="79394-185">Se si dispone di più sottoscrizioni, selezionare il nome della sottoscrizione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="79394-185">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="79394-186">In **ID partner** selezionare **Modifica Partner of Record**.</span><span class="sxs-lookup"><span data-stu-id="79394-186">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="79394-187">Nella pagina **Informazioni partner** deselezionare la casella **ID partner** e fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="79394-187">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>

::: moniker-end

## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="79394-188">Rimuovere una relazione rivenditore</span><span class="sxs-lookup"><span data-stu-id="79394-188">Remove a reseller relationship</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="79394-189">Non è possibile rimuovere una relazione come rivenditore autonomamente.</span><span class="sxs-lookup"><span data-stu-id="79394-189">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="79394-190">Se stai rimuovendo una  relazione rivenditore, l'opzione Elimina è disattivata e devi chiedere al partner rivenditore di seguire queste istruzioni: Rimuovere una relazione di rivenditore [con il partner](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="79394-190">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="79394-191">Non è possibile rimuovere una relazione come rivenditore autonomamente.</span><span class="sxs-lookup"><span data-stu-id="79394-191">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="79394-192">Se stai rimuovendo una  relazione rivenditore, l'opzione Elimina è disattivata e devi chiedere al partner rivenditore di seguire queste istruzioni: Rimuovere una relazione di rivenditore [con il partner](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="79394-192">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="79394-193">Non è possibile rimuovere una relazione come rivenditore autonomamente.</span><span class="sxs-lookup"><span data-stu-id="79394-193">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="79394-194">È necessario chiedere al partner rivenditore di seguire queste istruzioni: Rimuovere una relazione [di rivenditore con il partner](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="79394-194">You will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-content"></a><span data-ttu-id="79394-195">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="79394-195">Related content</span></span>

<span data-ttu-id="79394-196">[Trovare il Microsoft 365 partner o rivenditore](../manage/find-your-partner-or-reseller.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="79394-196">[Find your Microsoft 365 partner or reseller](../manage/find-your-partner-or-reseller.md) (article)</span></span>\
<span data-ttu-id="79394-197">[Pianificare la configurazione di Microsoft 365 per le aziende](../setup/plan-your-setup.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="79394-197">[Plan your setup of Microsoft 365 for business](../setup/plan-your-setup.md) (article)</span></span>