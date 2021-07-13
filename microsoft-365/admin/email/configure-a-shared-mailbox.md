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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Creare una cassetta postale condivisa e configurare alcune impostazioni per gli utenti, ad esempio l'inoltro della posta elettronica e le risposte automatiche.
ms.openlocfilehash: e69d1bbde5784339f3973bf456eca1ded72840af
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393992"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="0cd4c-103">Configurare le impostazioni della cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0cd4c-103">Configure shared mailbox settings</span></span>

<span data-ttu-id="0cd4c-104">Dopo aver creato [una cassetta](create-a-shared-mailbox.md)postale condivisa, è necessario configurare alcune impostazioni per gli utenti della cassetta postale, ad esempio l'inoltro della posta elettronica e le risposte automatiche.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-104">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="0cd4c-105">In seguito, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome della cassetta postale, i membri o le autorizzazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-105">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="0cd4c-106">Modificare il nome o l'alias di posta elettronica di una cassetta postale condivisa o l'indirizzo di posta elettronica principale</span><span class="sxs-lookup"><span data-stu-id="0cd4c-106">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="0cd4c-107">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-107">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="0cd4c-108">Selezionare la cassetta postale condivisa che si desidera modificare, quindi **selezionare** Modifica accanto a **Nome, Posta elettronica, Alias di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-108">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="0cd4c-109">Immettere un nuovo nome o aggiungere un altro alias.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-109">Enter a new name, or add another alias.</span></span> <span data-ttu-id="0cd4c-110">Se si desidera modificare l'indirizzo di posta elettronica principale, la cassetta postale deve disporre di più alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-110">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="0cd4c-111">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-111">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="0cd4c-112">Inoltrare messaggi di posta elettronica inviati a una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0cd4c-112">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="0cd4c-113">Non è necessario assegnare una licenza alla cassetta postale condivisa per inoltrare la posta elettronica inviata.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-113">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="0cd4c-114">È possibile inoltrare i messaggi a qualsiasi indirizzo di posta elettronica o lista di distribuzione valida.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-114">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="0cd4c-115">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-115">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="0cd4c-116">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Inoltro posta elettronica** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-116">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="0cd4c-117">Impostare l'interruttore **su Attivato** e immettere un indirizzo di posta elettronica a cui inoltrare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-117">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="0cd4c-118">Può essere qualsiasi indirizzo di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-118">It can be any valid email address.</span></span> <span data-ttu-id="0cd4c-119">Per inoltrare più indirizzi, è necessario [creare](/office365/admin/setup/create-distribution-lists) un gruppo di distribuzione per gli indirizzi e quindi immettere il nome del gruppo in questa casella.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-119">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="0cd4c-120">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-120">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="0cd4c-121">Inviare risposte automatiche da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0cd4c-121">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="0cd4c-122">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="0cd4c-123">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Risposte automatiche** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-123">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="0cd4c-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="0cd4c-p105">Immettere la risposta da inviare alle persone interne all'organizzazione. Non è possibile aggiungere immagini, solo testo.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p105">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="0cd4c-127">Se si desidera *inviare* anche una risposta a persone esterne all'organizzazione, selezionare la casella di controllo, a chi si desidera inviare la risposta e digitare il testo.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-127">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="0cd4c-128">Non è possibile inviare risposte solo a persone esterne all'organizzazione, escludendo quelle interne.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-128">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="0cd4c-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-129">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="0cd4c-130">Consentire a tutti di visualizzare la posta inviata (le risposte)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-130">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="0cd4c-p107">Per impostazione predefinita, i messaggi inviati dalla cassetta postale condivisa non vengono salvati nella relativa cartella Posta inviata, bensì nella cartella Posta inviata della persona che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p107">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="0cd4c-133">Se si desidera consentire a tutti di visualizzare la posta elettronica inviata, nell'interfaccia di amministrazione modificare le impostazioni della cassetta postale condivisa e selezionare **Posta inviata** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-133">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="0cd4c-134">Scegliere le app che una cassetta postale condivisa può usare per accedere alla posta elettronica Microsoft</span><span class="sxs-lookup"><span data-stu-id="0cd4c-134">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="0cd4c-135">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-135">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="0cd4c-136">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **App di posta elettronica** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-136">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="0cd4c-137">Imposta l'interruttore **su Attivato** per tutte le app che vuoi che i membri possano usare per accedere alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-137">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="0cd4c-138">Imposta l'interruttore **su Disattivato** per tutte le app che non vuoi che usino.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-138">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="0cd4c-139">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-139">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="0cd4c-140">Blocco per controversia legale per una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="0cd4c-140">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="0cd4c-141">Per ulteriori informazioni sulla conservazione per controversia legale, vedere [Create a Litigation Hold.](../../compliance/create-a-litigation-hold.md)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-141">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="0cd4c-142">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="0cd4c-143">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare Conservazione **per controversia legale** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-143">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="0cd4c-144">Impostare l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-144">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="0cd4c-145">Facoltativamente, immettere una durata, una nota sul blocco e un URL con ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-145">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="0cd4c-146">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-146">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="0cd4c-147">Aggiungere o rimuovere membri</span><span class="sxs-lookup"><span data-stu-id="0cd4c-147">Add or remove members</span></span>

1. <span data-ttu-id="0cd4c-148">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-148">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="0cd4c-149">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Membri** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-149">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="0cd4c-150">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cd4c-150">Do one of the following:</span></span>
   - <span data-ttu-id="0cd4c-151">Per aggiungere membri, selezionare **Aggiungi membri,** cercare o selezionare un membro da aggiungere e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-151">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="0cd4c-152">Per rimuovere i membri, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-152">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="0cd4c-153">Selezionare **di nuovo Salva.**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-153">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="0cd4c-154">Aggiungere o rimuovere le autorizzazioni dei membri</span><span class="sxs-lookup"><span data-stu-id="0cd4c-154">Add or remove permissions of members</span></span>

1. <span data-ttu-id="0cd4c-155">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="0cd4c-156">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Membri** \> **Personalizza autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-156">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="0cd4c-157">Selezionare **Modifica** accanto all'autorizzazione che si desidera modificare per un membro.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-157">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="0cd4c-158">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cd4c-158">Do one of the following:</span></span>
   - <span data-ttu-id="0cd4c-159">Per concedere l'autorizzazione a un altro membro, selezionare **Aggiungi autorizzazioni,** cercare o selezionare un membro da aggiungere e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-159">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="0cd4c-160">Per rimuovere l'autorizzazione da un membro, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-160">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="0cd4c-161">Selezionare **di nuovo Salva.**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-161">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="0cd4c-162">Mostrare o nascondere una cassetta postale condivisa nell'elenco indirizzi globale</span><span class="sxs-lookup"><span data-stu-id="0cd4c-162">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="0cd4c-163">Se si sceglie di non visualizzare la cassetta postale condivisa nell'elenco indirizzi globale, la cassetta postale non verrà visualizzata nell'elenco indirizzi dell'organizzazione, ma riceverà comunque la posta elettronica inviata.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-163">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="0cd4c-164">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-164">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="0cd4c-165">Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Mostra nell'elenco indirizzi globale** \> **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-165">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="0cd4c-166">Impostare l'interruttore **su Attivato** o **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-166">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="0cd4c-167">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-167">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="0cd4c-168">Nascondere una cassetta postale condivisa dall'elenco indirizzi rende impossibile per i nuovi membri della cassetta postale condivisa aggiungere la cassetta postale nascosta al proprio profilo Outlook fino a quando la cassetta postale condivisa non viene nuovamente visualizzata nell'elenco indirizzi.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-168">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="0cd4c-169">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="0cd4c-169">Related content</span></span>

<span data-ttu-id="0cd4c-170">[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-170">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="0cd4c-171">[Creare una cassetta postale condivisa](create-a-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-171">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="0cd4c-172">[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-172">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="0cd4c-173">[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-173">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="0cd4c-174">[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-174">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>