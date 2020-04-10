---
title: Configurare una cassetta postale condivisa
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
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Dopo aver creato una cassetta postale condivisa, è necessario configurare alcune impostazioni per gli utenti, ad esempio l'inoltro della posta elettronica e le risposte automatiche. Successivamente, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome della cassetta postale o i membri.
ms.openlocfilehash: fc2995dc448c7cb28c13c10d78b57e7141963539
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212022"
---
# <a name="configure-a-shared-mailbox"></a><span data-ttu-id="b6151-104">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="b6151-104">Configure a shared mailbox</span></span>

<span data-ttu-id="b6151-105">Dopo aver [creato una cassetta postale condivisa](create-a-shared-mailbox.md), è necessario configurare alcune impostazioni per gli utenti delle cassette postali, ad esempio l'inoltro della posta elettronica e le risposte automatiche.</span><span class="sxs-lookup"><span data-stu-id="b6151-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="b6151-106">Successivamente, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome della cassetta postale, i membri o le autorizzazioni per i membri.</span><span class="sxs-lookup"><span data-stu-id="b6151-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="b6151-107">Modificare il nome o l'alias di posta elettronica di una cassetta postale condivisa o modificare l'indirizzo di posta elettronica principale</span><span class="sxs-lookup"><span data-stu-id="b6151-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6151-108">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="b6151-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="b6151-109">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6151-110">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="b6151-111">Selezionare la cassetta postale condivisa che si desidera modificare e quindi fare clic su **modifica** accanto a **nome, posta elettronica, alias di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="b6151-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="b6151-112">Immettere un nuovo nome o aggiungere un altro alias.</span><span class="sxs-lookup"><span data-stu-id="b6151-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="b6151-113">Se si desidera modificare l'indirizzo di posta elettronica principale, la cassetta postale deve disporre di più di un alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b6151-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="b6151-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="b6151-115">Inoltrare messaggi di posta elettronica inviati a una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="b6151-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="b6151-116">Non è necessario assegnare una licenza alla cassetta postale condivisa per inoltrare la posta elettronica inviata.</span><span class="sxs-lookup"><span data-stu-id="b6151-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="b6151-117">È possibile inoltrare i messaggi a qualsiasi indirizzo di posta elettronica o elenco di distribuzione valido.</span><span class="sxs-lookup"><span data-stu-id="b6151-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6151-118">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="b6151-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="b6151-119">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6151-120">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="b6151-121">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare \> **modifica** **inoltro della posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="b6151-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="b6151-122">Impostare l'interruttore **su**attivato e immettere un indirizzo di posta elettronica a cui inoltrare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="b6151-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="b6151-123">Può essere un qualsiasi indirizzo di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="b6151-123">It can be any valid email address.</span></span> <span data-ttu-id="b6151-124">Per inoltrare a più indirizzi, è necessario [creare un gruppo di distribuzione](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) per gli indirizzi e quindi immettere il nome del gruppo in questa casella.</span><span class="sxs-lookup"><span data-stu-id="b6151-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="b6151-125">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="b6151-126">Inviare risposte automatiche da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="b6151-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6151-127">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="b6151-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="b6151-128">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6151-129">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="b6151-130">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare \> **modifica** **risposte automatiche** .</span><span class="sxs-lookup"><span data-stu-id="b6151-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="b6151-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span><span class="sxs-lookup"><span data-stu-id="b6151-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="b6151-132">Immettere la risposta da inviare alle persone interne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6151-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="b6151-133">Non è possibile aggiungere immagini, solo testo.</span><span class="sxs-lookup"><span data-stu-id="b6151-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="b6151-134">Se si desidera inviare una risposta *anche* alle persone esterne all'organizzazione, selezionare la casella di controllo, per cui si desidera ottenere la risposta e digitare il testo.</span><span class="sxs-lookup"><span data-stu-id="b6151-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="b6151-135">Non è possibile inviare risposte solo a persone esterne all'organizzazione, escludendo quelle interne.</span><span class="sxs-lookup"><span data-stu-id="b6151-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="b6151-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="b6151-137">Consentire a tutti di visualizzare la posta inviata (le risposte)</span><span class="sxs-lookup"><span data-stu-id="b6151-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="b6151-p108">Per impostazione predefinita, i messaggi inviati dalla cassetta postale condivisa non vengono salvati nella relativa cartella Posta inviata, bensì nella cartella Posta inviata della persona che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b6151-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="b6151-140">Se si desidera consentire a tutti di visualizzare il messaggio di posta elettronica inviato, nell'interfaccia di amministrazione modificare le impostazioni della cassetta postale condivisa e selezionare \> **modifica** **elementi inviati** .</span><span class="sxs-lookup"><span data-stu-id="b6151-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-office-365-email"></a><span data-ttu-id="b6151-141">Scegliere le app che possono essere utilizzate da una cassetta postale condivisa per accedere alla posta elettronica di Office 365</span><span class="sxs-lookup"><span data-stu-id="b6151-141">Choose the apps that a shared mailbox can use to access Office 365 email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6151-142">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="b6151-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="b6151-143">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6151-144">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="b6151-145">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare \> **modifica** **app di posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="b6151-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="b6151-146">Impostare l'interruttore **su** attivato per tutte le app che si desidera siano in grado di utilizzare per accedere alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="b6151-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="b6151-147">Impostare l'interruttore su **disattivato** per tutte le applicazioni che non si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b6151-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="b6151-148">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="b6151-149">Inserire una cassetta postale condivisa sul blocco per controversia legale</span><span class="sxs-lookup"><span data-stu-id="b6151-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="b6151-150">Per ulteriori informazioni sul blocco per controversia legale, vedere [creare un blocco per controversia legale](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="b6151-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6151-151">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="b6151-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="b6151-152">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6151-153">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="b6151-154">Selezionare la cassetta postale condivisa che si \> **desidera modificare,** quindi selezionare **blocco per controversia legale** .</span><span class="sxs-lookup"><span data-stu-id="b6151-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="b6151-155">Impostare l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="b6151-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="b6151-156">Facoltativamente, immettere una durata, una nota s relativa all'esenzione e un URL con ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="b6151-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="b6151-157">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="b6151-158">Aggiungere o rimuovere membri</span><span class="sxs-lookup"><span data-stu-id="b6151-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6151-159">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="b6151-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="b6151-160">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6151-161">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="b6151-162">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **membri** \> **Edit**.</span><span class="sxs-lookup"><span data-stu-id="b6151-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="b6151-163">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6151-163">Do one of the following:</span></span>
   - <span data-ttu-id="b6151-164">Per aggiungere membri, selezionare **Aggiungi membri**, cercare o selezionare un membro da aggiungere e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="b6151-165">Per rimuovere membri, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="b6151-166">Selezionare **Salva** di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b6151-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="b6151-167">Aggiungere o rimuovere autorizzazioni per i membri</span><span class="sxs-lookup"><span data-stu-id="b6151-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6151-168">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="b6151-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="b6151-169">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6151-170">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="b6151-171">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **membri** \> **Customize Permissions**.</span><span class="sxs-lookup"><span data-stu-id="b6151-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="b6151-172">Selezionare **modifica** accanto all'autorizzazione che si desidera modificare per un membro.</span><span class="sxs-lookup"><span data-stu-id="b6151-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="b6151-173">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6151-173">Do one of the following:</span></span>
   - <span data-ttu-id="b6151-174">Per concedere tale autorizzazione a un membro aggiuntivo, selezionare **Aggiungi autorizzazioni**, cercare o selezionare un membro da aggiungere e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="b6151-175">Per rimuovere l'autorizzazione da un membro, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="b6151-176">Selezionare **Salva** di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b6151-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="b6151-177">Mostrare o nascondere una cassetta postale condivisa nell'elenco indirizzi globale</span><span class="sxs-lookup"><span data-stu-id="b6151-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="b6151-178">Se si sceglie di non visualizzare la cassetta postale condivisa nell'elenco indirizzi globale, la cassetta postale non verrà visualizzata nell'elenco indirizzi dell'organizzazione, ma riceverà comunque la posta elettronica inviata.</span><span class="sxs-lookup"><span data-stu-id="b6151-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b6151-179">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="b6151-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="b6151-180">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b6151-181">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="b6151-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="b6151-182">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Mostra in** \> **modifica**elenco indirizzi globale.</span><span class="sxs-lookup"><span data-stu-id="b6151-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="b6151-183">Impostare l'interruttore **su attivata** o **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b6151-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="b6151-184">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6151-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b6151-185">La disattivazione di una cassetta postale condivisa dall'elenco indirizzi renderà impossibile per i nuovi membri della cassetta postale condivisa aggiungere la cassetta postale nascosta al proprio profilo di Outlook fino a quando la cassetta postale condivisa non verrà nuovamente visualizzata nell'elenco indirizzi.</span><span class="sxs-lookup"><span data-stu-id="b6151-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="b6151-186">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b6151-186">Related articles</span></span>

[<span data-ttu-id="b6151-187">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="b6151-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="b6151-188">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="b6151-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="b6151-189">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="b6151-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="b6151-190">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="b6151-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="b6151-191">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="b6151-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
