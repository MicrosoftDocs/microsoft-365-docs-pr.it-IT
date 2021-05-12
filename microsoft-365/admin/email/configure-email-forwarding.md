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
ms.openlocfilehash: 4b205c0a21f076b9c7858c8a8fc46e240920cd32
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332631"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="4106c-103">Configurare l'inoltro della posta elettronica in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4106c-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="4106c-104">L'amministratore di un'organizzazione potrebbe avere requisiti aziendali per configurare l'inoltro della posta elettronica per la cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="4106c-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="4106c-105">L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4106c-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4106c-106">È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="4106c-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="4106c-107">Per ulteriori informazioni, vedere [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="4106c-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="4106c-108">Configurare l'inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="4106c-108">Configure email forwarding</span></span>

<span data-ttu-id="4106c-109">Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4106c-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="4106c-110">Dopo aver configurato l'inoltro della posta elettronica, **verranno** inoltrati solo i nuovi messaggi di posta elettronica inviati alla cassetta postale di origine. </span><span class="sxs-lookup"><span data-stu-id="4106c-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="4106c-111">L'inoltro della posta elettronica richiede che  *l'account from*  abbia una licenza.</span><span class="sxs-lookup"><span data-stu-id="4106c-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="4106c-112">Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato l'organizzazione, un'altra opzione è convertire la cassetta postale [in una cassetta postale condivisa.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="4106c-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="4106c-113">In questo modo diverse persone possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="4106c-113">This way several people can access it.</span></span> <span data-ttu-id="4106c-114">Tuttavia, una cassetta postale condivisa non può superare i 50 GB.</span><span class="sxs-lookup"><span data-stu-id="4106c-114">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="4106c-115">Per eseguire questa procedura, è necessario essere un amministratore di Exchange o un amministratore globale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4106c-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="4106c-116">Per ulteriori informazioni, vedere l'argomento [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4106c-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="4106c-117">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=834822)** attivi.</span><span class="sxs-lookup"><span data-stu-id="4106c-117">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="4106c-118">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica, quindi aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4106c-118">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="4106c-119">Nella scheda **Posta** selezionare Gestisci **inoltro posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="4106c-119">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="4106c-120">Nella pagina inoltro della posta elettronica, selezionare Inoltra tutti i messaggi di posta elettronica inviati a questa cassetta **postale,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="4106c-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="4106c-121">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="4106c-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="4106c-122">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="4106c-122">Select **Save changes**.</span></span>

    <span data-ttu-id="4106c-123">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="4106c-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="4106c-124">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="4106c-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="4106c-125">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4106c-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="4106c-126">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="4106c-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="4106c-127">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="4106c-127">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4106c-128">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=847686)** attivi.</span><span class="sxs-lookup"><span data-stu-id="4106c-128">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="4106c-129">Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4106c-129">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="4106c-130">Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="4106c-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="4106c-131">Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="4106c-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="4106c-132">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="4106c-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="4106c-133">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4106c-133">Select **Save**.</span></span>

   <span data-ttu-id="4106c-134">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="4106c-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="4106c-135">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="4106c-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="4106c-136">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4106c-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="4106c-137">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="4106c-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="4106c-138">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="4106c-138">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4106c-139">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=850628)** attivi.</span><span class="sxs-lookup"><span data-stu-id="4106c-139">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="4106c-140">Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4106c-140">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="4106c-141">Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="4106c-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="4106c-142">Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="4106c-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="4106c-143">Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="4106c-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="4106c-144">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4106c-144">Select **Save**.</span></span>

   <span data-ttu-id="4106c-145">**Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="4106c-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="4106c-146">Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="4106c-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="4106c-147">Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4106c-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="4106c-148">Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.</span><span class="sxs-lookup"><span data-stu-id="4106c-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="4106c-149">In caso contrario, l'inoltro della posta elettronica verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="4106c-149">If you do, email forwarding will stop.</span></span>

::: moniker-end

