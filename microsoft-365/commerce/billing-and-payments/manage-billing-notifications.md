---
title: Gestire le notifiche di fatturazione e gli allegati della fattura
f1.keywords:
- CSH
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
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Informazioni su come gestire chi riceve messaggi di posta elettronica di notifica della fatturazione e allegati di fattura.
ms.openlocfilehash: f0811c5d027d042b5114c9e05c698dab1e08763b
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515224"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="9a5c0-103">Gestire le notifiche di fatturazione e gli allegati della fattura</span><span class="sxs-lookup"><span data-stu-id="9a5c0-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="9a5c0-104">La **pagina Notifiche di fatturazione** consente di gestire chi riceve i messaggi di posta elettronica di notifica della fatturazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="9a5c0-105">La pagina offre anche la possibilità di ricevere le fatture [dell'organizzazione come allegati di posta elettronica.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="9a5c0-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9a5c0-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9a5c0-106">Before you begin</span></span>

<span data-ttu-id="9a5c0-107">Per eseguire i passaggi descritti in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="9a5c0-108">Gli amministratori della fatturazione possono apportare alcune di queste modifiche, come indicato nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="9a5c0-109">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9a5c0-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="9a5c0-110">Modificare la lingua in cui si riceve la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9a5c0-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="9a5c0-111">Gli amministratori della fatturazione possono anche eseguire i passaggi descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="9a5c0-112">I messaggi di posta elettronica di notifica della fatturazione vengono inviati nella lingua preferita dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="9a5c0-113">Per modificare la lingua preferita, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="9a5c0-114">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **Notifiche**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">fatturazione.</a></span><span class="sxs-lookup"><span data-stu-id="9a5c0-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="9a5c0-115">Nella sezione **Impostazioni notifica fatturazione** selezionare Modifica impostazioni di **notifica.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="9a5c0-116">Nel riquadro **Impostazioni notifica fatturazione,** in **Lingua preferita** selezionare la lingua che si desidera utilizzare, quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="9a5c0-117">Modificare chi riceve le notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a5c0-117">Change who receives billing notifications</span></span>

<span data-ttu-id="9a5c0-118">Le notifiche di fatturazione dell'organizzazione vengono inviate all'indirizzo di posta elettronica principale e alternativo di ogni amministratore globale e di fatturazione. Per modificare gli utenti con il ruolo di amministratore globale o fatturazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="9a5c0-119">Assegnare ruoli di amministratore tramite la pagina Notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a5c0-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="9a5c0-120">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="9a5c0-121">Nella sezione **Amministratori che ricevono le notifiche di fatturazione** selezionare il collegamento **Amministratore** fatturazione o Amministratore globale nel testo della descrizione. </span><span class="sxs-lookup"><span data-stu-id="9a5c0-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="9a5c0-122">Nel riquadro destro, nella scheda **Amministratori assegnati,** selezionare **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="9a5c0-123">Nel riquadro **Aggiungi amministratori** digitare il nome visualizzato o il nome utente dell'utente e quindi selezionare l'utente nell'elenco dei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="9a5c0-124">Aggiungere più utenti fino al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="9a5c0-125">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-125">Select **Save**.</span></span> <span data-ttu-id="9a5c0-126">L'utente viene aggiunto all'elenco degli amministratori assegnati.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="9a5c0-127">Rimuovere i ruoli di amministratore tramite la pagina Notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a5c0-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="9a5c0-128">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="9a5c0-129">Nella sezione **Amministratori che ricevono le notifiche di fatturazione** selezionare il collegamento **Amministratore** fatturazione o Amministratore globale nel testo della descrizione. </span><span class="sxs-lookup"><span data-stu-id="9a5c0-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="9a5c0-130">Nel riquadro destro, nella scheda **Amministratori** assegnati, selezionare gli utenti da rimuovere dal ruolo e quindi **selezionare Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="9a5c0-131">Nella casella di conferma selezionare **Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="9a5c0-132">L'utente viene rimosso dall'elenco degli amministratori assegnati.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="9a5c0-133">Modificare gli indirizzi di posta elettronica per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="9a5c0-133">Change the email addresses for admins</span></span>

<span data-ttu-id="9a5c0-134">Per modificare l'indirizzo di posta elettronica principale e alternativo di altri amministratori dell'organizzazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="9a5c0-135">Gli amministratori della fatturazione possono modificare i propri indirizzi di posta elettronica principali e alternativi, ma non per altri amministratori.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="9a5c0-136">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="9a5c0-137">Nella sezione **Admins receiving billing notifications** selezionare un nome.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="9a5c0-138">Nel riquadro destro aggiungere o aggiornare l'indirizzo di posta elettronica primario e alternativo in base alle esigenze, quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="9a5c0-139">Modificare l'indirizzo di posta elettronica di contatto dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="9a5c0-139">Change your organization's contact email</span></span>

<span data-ttu-id="9a5c0-140">Oltre agli amministratori globali e fatturazione, microsoft invia notifiche di fatturazione all'indirizzo di posta elettronica di contatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="9a5c0-141">Per modificare l'indirizzo di posta elettronica, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="9a5c0-142">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="9a5c0-143">In **Contatto dell'organizzazione che riceve le notifiche di fatturazione** selezionare il contatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="9a5c0-144">Nel riquadro destro digitare l'indirizzo di posta elettronica che si desidera utilizzare, quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="9a5c0-145">Ricevere le fatture dell'organizzazione come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9a5c0-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="9a5c0-146">Gli amministratori della fatturazione possono anche eseguire i passaggi descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="9a5c0-147">È possibile allegare una copia della fattura dell'organizzazione come file PDF ai messaggi di posta elettronica di notifica quando è pronta una nuova fattura.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="9a5c0-148">Per ricevere le fatture come allegati, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="9a5c0-149">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="9a5c0-150">In **Impostazioni notifica fatturazione** selezionare Modifica impostazioni di **notifica.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="9a5c0-151">Nel riquadro **Impostazioni notifica fatturazione,** sotto **Allega un PDF** ai messaggi di posta elettronica della fattura, seleziona la casella di controllo e quindi seleziona **Salva.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="9a5c0-152">Per interrompere la ricezione **dell'allegato** della fattura in qualsiasi momento, seguire i passaggi precedenti e deselezionare la casella di controllo Allega un PDF ai messaggi di posta elettronica della fattura nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="9a5c0-153">Cosa succede se si dispone di un profilo di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="9a5c0-153">What if I have a billing profile?</span></span>

<span data-ttu-id="9a5c0-154">Se si dispone di un profilo di fatturazione, alcuni dei passaggi descritti in questo articolo potrebbero essere leggermente diversi per alcuni abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="9a5c0-155">In questa sezione vengono descritte queste differenze.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-155">This section describes those differences.</span></span> [<span data-ttu-id="9a5c0-156">Come è possibile sapere se si dispone di un profilo di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="9a5c0-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="9a5c0-157">Chi riceve le notifiche di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="9a5c0-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="9a5c0-158">I messaggi di posta elettronica di notifica della fatturazione vengono inviati agli indirizzi di posta elettronica principali e alternativi per gli utenti a cui è assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5c0-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="9a5c0-159">Proprietario del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a5c0-159">Billing profile owner</span></span>
- <span data-ttu-id="9a5c0-160">Collaboratore del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a5c0-160">Billing profile contributor</span></span>
- <span data-ttu-id="9a5c0-161">Responsabile delle fatture</span><span class="sxs-lookup"><span data-stu-id="9a5c0-161">Invoice manager</span></span>

<span data-ttu-id="9a5c0-162">Per ulteriori informazioni sui ruoli del profilo di fatturazione e su come gestirli, vedere Comprendere i ruoli amministrativi del Contratto per i clienti [Microsoft in Azure.](https://docs.microsoft.com/azure/cost-management-billing/manage/understand-mca-roles)</span><span class="sxs-lookup"><span data-stu-id="9a5c0-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](https://docs.microsoft.com/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="9a5c0-163">Per modificare chi riceve le notifiche di fatturazione dell'organizzazione, eseguire la procedura seguente per modificare i ruoli assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="9a5c0-164">Nell'interfaccia di amministrazione passare alla pagina **Fatture**&  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">pagamenti.</a></span><span class="sxs-lookup"><span data-stu-id="9a5c0-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="9a5c0-165">Nella scheda **Profilo di fatturazione** selezionare un profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="9a5c0-166">Nella sezione **Ruoli profilo di** fatturazione assegnare o rimuovere ruoli per proprietario del profilo di fatturazione, **collaboratore** del profilo di fatturazione o **responsabile della fattura.** </span><span class="sxs-lookup"><span data-stu-id="9a5c0-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="9a5c0-167">Ricevere fatture come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9a5c0-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="9a5c0-168">Per ricevere le fatture come allegati alle notifiche di fatturazione, usa la procedura seguente per attivare questa impostazione per un profilo di fatturazione specifico.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="9a5c0-169">Nell'interfaccia di amministrazione passare alla pagina **Fatture**&  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">pagamenti.</a></span><span class="sxs-lookup"><span data-stu-id="9a5c0-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="9a5c0-170">Seleziona la **scheda Profili di** fatturazione, quindi seleziona un profilo di fatturazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="9a5c0-171">Nella pagina dei dettagli del profilo di fatturazione, **in Ottieni fatture negli allegati di posta elettronica,** impostare l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="9a5c0-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="9a5c0-172">Contenuti correlati</span><span class="sxs-lookup"><span data-stu-id="9a5c0-172">Related content</span></span>

<span data-ttu-id="9a5c0-173">[Visualizzare la fattura](view-your-bill-or-invoice.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="9a5c0-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="9a5c0-174">[Comprendere la fattura per Microsoft 365 per le aziende](understand-your-invoice2.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="9a5c0-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="9a5c0-175">[Aggiungere utenti e assegnare licenze contemporaneamente](../../admin/add-users/add-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="9a5c0-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>