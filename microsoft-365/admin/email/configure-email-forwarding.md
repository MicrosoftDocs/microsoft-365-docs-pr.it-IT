---
title: Configurare l'inoltro della posta elettronica
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: L'inoltro della posta elettronica consente di inoltrare i messaggi di posta elettronica inviati a una Microsoft 365 utente a un'altra cassetta postale all'interno o all'esterno dell'organizzazione.
ms.openlocfilehash: 1d16a44749b51b582b7198cb331edf7faf3cf1f8
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698917"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="c895a-103">Configurare l'inoltro della posta elettronica in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c895a-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="c895a-104">L'amministratore di un'organizzazione potrebbe avere requisiti aziendali per configurare l'inoltro della posta elettronica per la cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="c895a-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="c895a-105">L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c895a-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c895a-106">È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="c895a-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="c895a-107">Per ulteriori informazioni, vedere [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="c895a-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="c895a-108">Configurare l'inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c895a-108">Configure email forwarding</span></span>

<span data-ttu-id="c895a-109">Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c895a-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="c895a-110">Consenti l'invio automatico dei messaggi inoltrati agli utenti del dominio remoto.</span><span class="sxs-lookup"><span data-stu-id="c895a-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="c895a-111">Per [informazioni dettagliate, vedere](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) Manage remote domains.</span><span class="sxs-lookup"><span data-stu-id="c895a-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="c895a-112">Dopo aver configurato l'inoltro della posta elettronica, **verranno** inoltrati solo i nuovi messaggi di posta elettronica inviati alla cassetta postale di origine. </span><span class="sxs-lookup"><span data-stu-id="c895a-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="c895a-113">L'inoltro della posta elettronica richiede che  *l'account from*  abbia una licenza.</span><span class="sxs-lookup"><span data-stu-id="c895a-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="c895a-114">Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato l'organizzazione, un'altra opzione è convertire la cassetta postale [in una cassetta postale condivisa.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="c895a-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="c895a-115">In questo modo diverse persone possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="c895a-115">This way several people can access it.</span></span> <span data-ttu-id="c895a-116">Tuttavia, una cassetta postale condivisa non può superare i 50 GB.</span><span class="sxs-lookup"><span data-stu-id="c895a-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="c895a-117">Per eseguire questa Microsoft 365, è necessario essere un amministratore Exchange o un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c895a-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="c895a-118">Per ulteriori informazioni, vedere l'argomento [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c895a-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="c895a-119">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=834822)** attivi.</span><span class="sxs-lookup"><span data-stu-id="c895a-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="c895a-120">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica, quindi aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="c895a-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="c895a-121">Nella scheda **Posta** selezionare Gestisci **inoltro posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="c895a-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="c895a-122">Nella pagina inoltro della posta elettronica, selezionare Inoltra tutti i messaggi di posta elettronica inviati a questa cassetta **postale,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="c895a-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c895a-123">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="c895a-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c895a-124">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="c895a-124">Select **Save changes**.</span></span>

    <span data-ttu-id="c895a-125">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="c895a-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c895a-126">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="c895a-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="c895a-127">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c895a-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c895a-128">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="c895a-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c895a-129">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="c895a-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c895a-130">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=847686)** attivi.</span><span class="sxs-lookup"><span data-stu-id="c895a-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="c895a-131">Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="c895a-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="c895a-132">Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="c895a-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c895a-133">Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="c895a-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c895a-134">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="c895a-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c895a-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c895a-135">Select **Save**.</span></span>

   <span data-ttu-id="c895a-136">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="c895a-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c895a-137">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="c895a-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="c895a-138">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c895a-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c895a-139">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="c895a-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="c895a-140">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="c895a-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c895a-141">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=850628)** attivi.</span><span class="sxs-lookup"><span data-stu-id="c895a-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="c895a-142">Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="c895a-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="c895a-143">Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="c895a-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="c895a-144">Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="c895a-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="c895a-145">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="c895a-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="c895a-146">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c895a-146">Select **Save**.</span></span>

   <span data-ttu-id="c895a-147">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="c895a-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="c895a-148">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="c895a-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="c895a-149">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c895a-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="c895a-150">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="c895a-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="c895a-151">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="c895a-151">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="c895a-152">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="c895a-152">Related content</span></span> 

<span data-ttu-id="c895a-153">[Creare una cassetta postale condivisa](../email/create-a-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c895a-153">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="c895a-154">[Inviare messaggi di posta elettronica da un indirizzo diverso](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c895a-154">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="c895a-155">[Modificare un nome utente e un indirizzo di posta elettronica](../add-users/change-a-user-name-and-email-address.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c895a-155">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
