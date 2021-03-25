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
description: Configurare l'inoltro della posta elettronica a uno o più account di posta elettronica tramite Office365.
ms.openlocfilehash: d7c9a37a066bd53e541cf623c1953fb572827b61
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197864"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="e0512-103">Configurare l'inoltro della posta elettronica in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0512-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e0512-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="e0512-104">The admin center is changing.</span></span> <span data-ttu-id="e0512-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e0512-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e0512-106">L'amministratore di un'organizzazione potrebbe avere requisiti aziendali per configurare l'inoltro della posta elettronica per la cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="e0512-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="e0512-107">L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0512-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0512-108">È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="e0512-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="e0512-109">Per ulteriori informazioni, vedere [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="e0512-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="e0512-110">Configurare l'inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="e0512-110">Configure email forwarding</span></span>

<span data-ttu-id="e0512-111">Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e0512-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="e0512-112">Dopo aver configurato l'inoltro della posta elettronica, **verranno** inoltrati solo i nuovi messaggi di posta elettronica inviati alla cassetta postale di origine. </span><span class="sxs-lookup"><span data-stu-id="e0512-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="e0512-113">L'inoltro della posta elettronica richiede che  *l'account from*  abbia una licenza.</span><span class="sxs-lookup"><span data-stu-id="e0512-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="e0512-114">Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato l'organizzazione, un'altra opzione è convertire la cassetta postale [in una cassetta postale condivisa.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="e0512-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="e0512-115">In questo modo diverse persone possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="e0512-115">This way several people can access it.</span></span> <span data-ttu-id="e0512-116">Tuttavia, una cassetta postale condivisa non può superare i 50 GB.</span><span class="sxs-lookup"><span data-stu-id="e0512-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="e0512-117">Per eseguire questa procedura, è necessario essere un amministratore di Exchange o un amministratore globale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0512-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="e0512-118">Per ulteriori informazioni, vedere l'argomento [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="e0512-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e0512-119">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=834822)** attivi.</span><span class="sxs-lookup"><span data-stu-id="e0512-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="e0512-120">Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="e0512-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="e0512-121">Nella scheda **Posta** selezionare Gestisci **inoltro posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="e0512-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="e0512-122">Nella pagina inoltro della posta elettronica, selezionare Inoltra tutti i messaggi di posta elettronica inviati a questa cassetta **postale,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="e0512-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e0512-123">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="e0512-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e0512-124">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="e0512-124">Select **Save changes**.</span></span>

    <span data-ttu-id="e0512-125">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="e0512-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e0512-126">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e0512-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="e0512-127">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e0512-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="e0512-128">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="e0512-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e0512-129">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="e0512-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e0512-130">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=847686)** attivi.</span><span class="sxs-lookup"><span data-stu-id="e0512-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="e0512-131">Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="e0512-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="e0512-132">Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="e0512-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="e0512-133">Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="e0512-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e0512-134">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="e0512-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e0512-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0512-135">Select **Save**.</span></span>

   <span data-ttu-id="e0512-136">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="e0512-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e0512-137">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e0512-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="e0512-138">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e0512-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="e0512-139">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="e0512-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e0512-140">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="e0512-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e0512-141">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=850628)** attivi.</span><span class="sxs-lookup"><span data-stu-id="e0512-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="e0512-142">Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="e0512-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="e0512-143">Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="e0512-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="e0512-144">Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="e0512-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="e0512-145">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="e0512-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="e0512-146">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0512-146">Select **Save**.</span></span>

   <span data-ttu-id="e0512-147">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="e0512-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="e0512-148">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="e0512-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="e0512-149">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e0512-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="e0512-150">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="e0512-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="e0512-151">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="e0512-151">If you do, email forwarding will stop.</span></span>

::: moniker-end