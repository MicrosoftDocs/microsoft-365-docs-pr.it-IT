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
search.appverid:
- BCS160
- MET150
- MOE150
description: Dopo aver creato una cassetta postale condivisa, è necessario configurare alcune impostazioni per i relativi utenti, ad esempio l'inoltro della posta elettronica e le risposte automatiche. In seguito, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome o i membri della cassetta postale.
ms.openlocfilehash: 01d5aaa686e1d64c9ea7d89913d8208f779dcfd1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52243973"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="62a44-104">Configurare le impostazioni della cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="62a44-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="62a44-105">Dopo aver creato [una cassetta](create-a-shared-mailbox.md)postale condivisa, è necessario configurare alcune impostazioni per gli utenti della cassetta postale, ad esempio l'inoltro della posta elettronica e le risposte automatiche.</span><span class="sxs-lookup"><span data-stu-id="62a44-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="62a44-106">In seguito, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome della cassetta postale, i membri o le autorizzazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="62a44-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="62a44-107">Modificare il nome o l'alias di posta elettronica di una cassetta postale condivisa o l'indirizzo di posta elettronica principale</span><span class="sxs-lookup"><span data-stu-id="62a44-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="62a44-108">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="62a44-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="62a44-109">Selezionare la cassetta postale condivisa che si desidera modificare, quindi **selezionare** Modifica accanto a **Nome, Posta elettronica, Alias di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="62a44-109">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="62a44-110">Immettere un nuovo nome o aggiungere un altro alias.</span><span class="sxs-lookup"><span data-stu-id="62a44-110">Enter a new name, or add another alias.</span></span> <span data-ttu-id="62a44-111">Se si desidera modificare l'indirizzo di posta elettronica principale, la cassetta postale deve disporre di più alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="62a44-111">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="62a44-112">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-112">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="62a44-113">Inoltrare messaggi di posta elettronica inviati a una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="62a44-113">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="62a44-114">Non è necessario assegnare una licenza alla cassetta postale condivisa per inoltrare la posta elettronica inviata.</span><span class="sxs-lookup"><span data-stu-id="62a44-114">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="62a44-115">È possibile inoltrare i messaggi a qualsiasi indirizzo di posta elettronica o lista di distribuzione valida.</span><span class="sxs-lookup"><span data-stu-id="62a44-115">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="62a44-116">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="62a44-116">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="62a44-117">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Inoltro posta elettronica** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="62a44-117">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="62a44-118">Impostare l'interruttore **su Attivato** e immettere un indirizzo di posta elettronica a cui inoltrare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="62a44-118">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="62a44-119">Può essere qualsiasi indirizzo di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="62a44-119">It can be any valid email address.</span></span> <span data-ttu-id="62a44-120">Per inoltrare più indirizzi, è necessario [creare](/office365/admin/setup/create-distribution-lists) un gruppo di distribuzione per gli indirizzi e quindi immettere il nome del gruppo in questa casella.</span><span class="sxs-lookup"><span data-stu-id="62a44-120">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="62a44-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-121">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="62a44-122">Inviare risposte automatiche da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="62a44-122">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="62a44-123">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="62a44-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="62a44-124">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Risposte automatiche** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="62a44-124">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="62a44-125">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span><span class="sxs-lookup"><span data-stu-id="62a44-125">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="62a44-p106">Immettere la risposta da inviare alle persone interne all'organizzazione. Non è possibile aggiungere immagini, solo testo.</span><span class="sxs-lookup"><span data-stu-id="62a44-p106">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="62a44-128">Se si desidera *inviare* anche una risposta a persone esterne all'organizzazione, selezionare la casella di controllo, a chi si desidera inviare la risposta e digitare il testo.</span><span class="sxs-lookup"><span data-stu-id="62a44-128">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="62a44-129">Non è possibile inviare risposte solo a persone esterne all'organizzazione, escludendo quelle interne.</span><span class="sxs-lookup"><span data-stu-id="62a44-129">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="62a44-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-130">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="62a44-131">Consentire a tutti di visualizzare la posta inviata (le risposte)</span><span class="sxs-lookup"><span data-stu-id="62a44-131">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="62a44-p108">Per impostazione predefinita, i messaggi inviati dalla cassetta postale condivisa non vengono salvati nella relativa cartella Posta inviata, bensì nella cartella Posta inviata della persona che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="62a44-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="62a44-134">Se si desidera consentire a tutti di visualizzare la posta elettronica inviata, nell'interfaccia di amministrazione modificare le impostazioni della cassetta postale condivisa e selezionare **Posta inviata** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="62a44-134">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="62a44-135">Scegliere le app che una cassetta postale condivisa può usare per accedere alla posta elettronica Microsoft</span><span class="sxs-lookup"><span data-stu-id="62a44-135">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="62a44-136">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="62a44-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="62a44-137">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **App di posta elettronica** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="62a44-137">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="62a44-138">Imposta l'interruttore **su Attivato** per tutte le app che vuoi che i membri possano usare per accedere alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="62a44-138">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="62a44-139">Imposta l'interruttore **su Disattivato** per tutte le app che non vuoi che usino.</span><span class="sxs-lookup"><span data-stu-id="62a44-139">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="62a44-140">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-140">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="62a44-141">Blocco per controversia legale per una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="62a44-141">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="62a44-142">Per ulteriori informazioni sulla conservazione per controversia legale, vedere [Create a Litigation Hold.](../../compliance/create-a-litigation-hold.md)</span><span class="sxs-lookup"><span data-stu-id="62a44-142">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="62a44-143">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="62a44-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="62a44-144">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare Conservazione **per controversia legale** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="62a44-144">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="62a44-145">Impostare l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="62a44-145">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="62a44-146">Facoltativamente, immettere una durata, una nota sul blocco e un URL con ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="62a44-146">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="62a44-147">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-147">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="62a44-148">Aggiungere o rimuovere membri</span><span class="sxs-lookup"><span data-stu-id="62a44-148">Add or remove members</span></span>

1. <span data-ttu-id="62a44-149">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="62a44-149">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="62a44-150">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Membri** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="62a44-150">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="62a44-151">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62a44-151">Do one of the following:</span></span>
   - <span data-ttu-id="62a44-152">Per aggiungere membri, selezionare **Aggiungi membri,** cercare o selezionare un membro da aggiungere e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="62a44-152">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="62a44-153">Per rimuovere i membri, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-153">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="62a44-154">Selezionare **di nuovo Salva.**</span><span class="sxs-lookup"><span data-stu-id="62a44-154">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="62a44-155">Aggiungere o rimuovere le autorizzazioni dei membri</span><span class="sxs-lookup"><span data-stu-id="62a44-155">Add or remove permissions of members</span></span>

1. <span data-ttu-id="62a44-156">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="62a44-156">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="62a44-157">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Membri** \> **Personalizza autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="62a44-157">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="62a44-158">Selezionare **Modifica** accanto all'autorizzazione che si desidera modificare per un membro.</span><span class="sxs-lookup"><span data-stu-id="62a44-158">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="62a44-159">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62a44-159">Do one of the following:</span></span>
   - <span data-ttu-id="62a44-160">Per concedere l'autorizzazione a un altro membro, selezionare **Aggiungi autorizzazioni,** cercare o selezionare un membro da aggiungere e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-160">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="62a44-161">Per rimuovere l'autorizzazione da un membro, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-161">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="62a44-162">Selezionare **di nuovo Salva.**</span><span class="sxs-lookup"><span data-stu-id="62a44-162">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="62a44-163">Mostrare o nascondere una cassetta postale condivisa nell'elenco indirizzi globale</span><span class="sxs-lookup"><span data-stu-id="62a44-163">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="62a44-164">Se si sceglie di non visualizzare la cassetta postale condivisa nell'elenco indirizzi globale, la cassetta postale non verrà visualizzata nell'elenco indirizzi dell'organizzazione, ma riceverà comunque la posta elettronica inviata.</span><span class="sxs-lookup"><span data-stu-id="62a44-164">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="62a44-165">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="62a44-165">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="62a44-166">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Mostra nell'elenco indirizzi globale** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="62a44-166">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="62a44-167">Impostare l'interruttore **su Attivato** o **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="62a44-167">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="62a44-168">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62a44-168">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="62a44-169">Nascondere una cassetta postale condivisa dall'elenco indirizzi rende impossibile per i nuovi membri della cassetta postale condivisa aggiungere la cassetta postale nascosta al proprio profilo Outlook fino a quando la cassetta postale condivisa non viene nuovamente visualizzata nell'elenco indirizzi.</span><span class="sxs-lookup"><span data-stu-id="62a44-169">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="62a44-170">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="62a44-170">Related content</span></span>

<span data-ttu-id="62a44-171">[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="62a44-171">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="62a44-172">[Creare una cassetta postale condivisa](create-a-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="62a44-172">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="62a44-173">[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="62a44-173">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="62a44-174">[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="62a44-174">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="62a44-175">[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="62a44-175">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>