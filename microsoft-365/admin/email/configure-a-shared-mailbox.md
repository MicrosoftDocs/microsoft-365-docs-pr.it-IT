---
title: Configurare le impostazioni della cassetta postale condivisa
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Dopo aver creato una cassetta postale condivisa, è possibile configurare alcune impostazioni per i relativi utenti, ad esempio l'inoltro della posta elettronica e le risposte automatiche. In seguito, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome o i membri della cassetta postale.
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926607"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="0bed0-104">Configurare le impostazioni della cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0bed0-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="0bed0-105">Dopo aver creato [una cassetta](create-a-shared-mailbox.md)postale condivisa, è possibile configurare alcune impostazioni per gli utenti della cassetta postale, ad esempio l'inoltro della posta elettronica e le risposte automatiche.</span><span class="sxs-lookup"><span data-stu-id="0bed0-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="0bed0-106">In seguito, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome della cassetta postale, i membri o le autorizzazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="0bed0-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="0bed0-107">Modificare il nome o l'alias di posta elettronica di una cassetta postale condivisa o l'indirizzo di posta elettronica principale</span><span class="sxs-lookup"><span data-stu-id="0bed0-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0bed0-108">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0bed0-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="0bed0-109">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0bed0-110">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="0bed0-111">Selezionare la cassetta postale condivisa che  si desidera modificare, quindi selezionare Modifica accanto a **Nome, Posta elettronica, Alias di posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="0bed0-112">Immettere un nuovo nome o aggiungere un altro alias.</span><span class="sxs-lookup"><span data-stu-id="0bed0-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="0bed0-113">Se si desidera modificare l'indirizzo di posta elettronica principale, la cassetta postale deve avere più alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0bed0-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="0bed0-114">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="0bed0-115">Inoltrare messaggi di posta elettronica inviati a una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0bed0-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="0bed0-116">Non è necessario assegnare una licenza alla cassetta postale condivisa per inoltrare la posta elettronica inviata.</span><span class="sxs-lookup"><span data-stu-id="0bed0-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="0bed0-117">È possibile inoltrare i messaggi a qualsiasi indirizzo di posta elettronica o lista di distribuzione valido.</span><span class="sxs-lookup"><span data-stu-id="0bed0-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0bed0-118">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0bed0-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="0bed0-119">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0bed0-120">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="0bed0-121">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Modifica inoltro posta** \> **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="0bed0-122">Impostare l'interruttore **su Attivato** e immettere un indirizzo di posta elettronica a cui inoltrare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="0bed0-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="0bed0-123">Può essere qualsiasi indirizzo di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="0bed0-123">It can be any valid email address.</span></span> <span data-ttu-id="0bed0-124">Per inoltrare a più [](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) indirizzi, è necessario creare un gruppo di distribuzione per gli indirizzi e quindi immettere il nome del gruppo in questa casella.</span><span class="sxs-lookup"><span data-stu-id="0bed0-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="0bed0-125">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="0bed0-126">Inviare risposte automatiche da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0bed0-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0bed0-127">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0bed0-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="0bed0-128">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0bed0-129">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="0bed0-130">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Modifica risposte** \> **automatiche.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="0bed0-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span><span class="sxs-lookup"><span data-stu-id="0bed0-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="0bed0-132">Immettere la risposta da inviare alle persone interne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bed0-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="0bed0-133">Non è possibile aggiungere immagini, solo testo.</span><span class="sxs-lookup"><span data-stu-id="0bed0-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="0bed0-134">Se si desidera *inviare* una risposta anche a persone esterne all'organizzazione, selezionare la casella di controllo, gli utenti a cui si desidera inviare la risposta e digitare il testo.</span><span class="sxs-lookup"><span data-stu-id="0bed0-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="0bed0-135">Non è possibile inviare risposte solo a persone esterne all'organizzazione, escludendo quelle interne.</span><span class="sxs-lookup"><span data-stu-id="0bed0-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="0bed0-136">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="0bed0-137">Consentire a tutti di visualizzare la posta inviata (le risposte)</span><span class="sxs-lookup"><span data-stu-id="0bed0-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="0bed0-p108">Per impostazione predefinita, i messaggi inviati dalla cassetta postale condivisa non vengono salvati nella relativa cartella Posta inviata, bensì nella cartella Posta inviata della persona che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="0bed0-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="0bed0-140">Se si desidera consentire a tutti di visualizzare la posta elettronica inviata, nell'interfaccia di amministrazione modificare le impostazioni della cassetta postale condivisa e selezionare **Posta inviata** \> **modifica.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="0bed0-141">Scegliere le app che una cassetta postale condivisa può usare per accedere alla posta elettronica Microsoft</span><span class="sxs-lookup"><span data-stu-id="0bed0-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0bed0-142">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0bed0-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="0bed0-143">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0bed0-144">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="0bed0-145">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Modifica app di posta** \> **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="0bed0-146">Impostare l'interruttore **su Attivato** per tutte le app che si desidera che i membri possano usare per accedere alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="0bed0-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="0bed0-147">Imposta l'interruttore **su Disattivato** per tutte le app che non vuoi che usino.</span><span class="sxs-lookup"><span data-stu-id="0bed0-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="0bed0-148">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="0bed0-149">Blocco per controversia legale per una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0bed0-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="0bed0-150">Per ulteriori informazioni sulla conservazione per controversia legale, vedere [Create a Litigation Hold.](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="0bed0-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0bed0-151">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0bed0-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="0bed0-152">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0bed0-153">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="0bed0-154">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare Modifica conservazione **per controversia** \> **legale.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="0bed0-155">Impostare l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="0bed0-156">Facoltativamente, immettere una durata, una nota sul blocco e un URL con altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0bed0-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="0bed0-157">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="0bed0-158">Aggiungere o rimuovere membri</span><span class="sxs-lookup"><span data-stu-id="0bed0-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0bed0-159">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0bed0-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="0bed0-160">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0bed0-161">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="0bed0-162">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Modifica** \> **membri.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="0bed0-163">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0bed0-163">Do one of the following:</span></span>
   - <span data-ttu-id="0bed0-164">Per aggiungere membri, selezionare **Aggiungi membri,** cercare o selezionare un membro da aggiungere e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="0bed0-165">Per rimuovere membri, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="0bed0-166">Selezionare **di nuovo Salva.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="0bed0-167">Aggiungere o rimuovere le autorizzazioni dei membri</span><span class="sxs-lookup"><span data-stu-id="0bed0-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0bed0-168">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0bed0-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="0bed0-169">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0bed0-170">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="0bed0-171">Selezionare la cassetta postale condivisa che si desidera modificare, quindi **selezionare** Membri \> **Personalizza autorizzazioni.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="0bed0-172">Selezionare **Modifica** accanto all'autorizzazione che si desidera modificare per un membro.</span><span class="sxs-lookup"><span data-stu-id="0bed0-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="0bed0-173">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0bed0-173">Do one of the following:</span></span>
   - <span data-ttu-id="0bed0-174">Per concedere tale autorizzazione a un altro membro, selezionare Aggiungi **autorizzazioni,** cercare o selezionare un membro da aggiungere e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="0bed0-175">Per rimuovere l'autorizzazione da un membro, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="0bed0-176">Selezionare **di nuovo Salva.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="0bed0-177">Mostrare o nascondere una cassetta postale condivisa nell'elenco indirizzi globale</span><span class="sxs-lookup"><span data-stu-id="0bed0-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="0bed0-178">Se si sceglie di non visualizzare la cassetta postale condivisa nell'elenco indirizzi globale, la cassetta postale non verrà visualizzata nell'elenco indirizzi dell'organizzazione, ma riceverà comunque messaggi di posta elettronica inviati.</span><span class="sxs-lookup"><span data-stu-id="0bed0-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0bed0-179">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0bed0-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="0bed0-180">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0bed0-181">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="0bed0-182">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Mostra nell'elenco indirizzi globale** \> **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="0bed0-183">Impostare l'interruttore su **Attivato** o **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0bed0-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="0bed0-184">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0bed0-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="0bed0-185">Nascondendo una cassetta postale condivisa dall'elenco indirizzi, non sarà possibile per i nuovi membri della cassetta postale condivisa aggiungere la cassetta postale nascosta al proprio profilo di Outlook finché la cassetta postale condivisa non viene nuovamente visualizzata nell'elenco indirizzi.</span><span class="sxs-lookup"><span data-stu-id="0bed0-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="0bed0-186">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="0bed0-186">Related articles</span></span>

[<span data-ttu-id="0bed0-187">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="0bed0-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="0bed0-188">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0bed0-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="0bed0-189">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0bed0-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="0bed0-190">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0bed0-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="0bed0-191">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="0bed0-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
