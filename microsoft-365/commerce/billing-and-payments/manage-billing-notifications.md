---
title: Gestire le notifiche di fatturazione e le fatture allegate
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
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
- commerce_billing
search.appverid:
- MET150
description: Informazioni su come gestire chi riceve messaggi di posta elettronica di notifica di fatturazione e allegati di fattura.
ms.date: 03/17/2021
ms.openlocfilehash: d4083dc5a9d70eb8c20b4107389ec5fec65749ad
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332139"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="e56fc-103">Gestire le notifiche di fatturazione e le fatture allegate</span><span class="sxs-lookup"><span data-stu-id="e56fc-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="e56fc-104">La **pagina Notifiche di** fatturazione consente di gestire chi riceve i messaggi di posta elettronica di notifica di fatturazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e56fc-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="e56fc-105">La pagina offre anche la possibilità di ricevere le fatture [dell'organizzazione come allegati di posta elettronica.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="e56fc-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e56fc-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e56fc-106">Before you begin</span></span>

<span data-ttu-id="e56fc-107">Per eseguire la procedura descritta in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e56fc-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="e56fc-108">Gli amministratori della fatturazione possono apportare alcune di queste modifiche, come indicato nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e56fc-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="e56fc-109">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e56fc-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="e56fc-110">Modificare la lingua in cui si riceve la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="e56fc-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="e56fc-111">Gli amministratori della fatturazione possono anche eseguire la procedura descritta in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e56fc-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="e56fc-112">I messaggi di posta elettronica di notifica di fatturazione vengono inviati nella lingua preferita dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e56fc-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="e56fc-113">Per modificare la lingua preferita, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e56fc-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="e56fc-114">Nell'Microsoft 365 di amministrazione passare alla pagina **Notifiche**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">fatturazione.</a></span><span class="sxs-lookup"><span data-stu-id="e56fc-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="e56fc-115">Nella sezione **Impostazioni notifiche di fatturazione** seleziona Modifica impostazioni **notifica.**</span><span class="sxs-lookup"><span data-stu-id="e56fc-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="e56fc-116">Nel riquadro **Impostazioni notifica fatturazione,** in **Lingua preferita** selezionare la lingua che si desidera utilizzare, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e56fc-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="e56fc-117">Modificare chi riceve le notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="e56fc-117">Change who receives billing notifications</span></span>

<span data-ttu-id="e56fc-118">Le notifiche di fatturazione dell'organizzazione vengono inviate all'indirizzo di posta elettronica principale e alternativo di ogni amministratore globale e fatturazione. Per modificare gli utenti con il ruolo di amministratore Globale o Fatturazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e56fc-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="e56fc-119">Assegnare ruoli di amministratore tramite la pagina Notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="e56fc-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="e56fc-120">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="e56fc-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="e56fc-121">Nella sezione **Amministratori che ricevono notifiche di fatturazione** selezionare il collegamento Amministratore fatturazione o **Amministratore** globale nel testo della descrizione. </span><span class="sxs-lookup"><span data-stu-id="e56fc-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="e56fc-122">Nel riquadro destro, nella **scheda Amministratori assegnati,** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e56fc-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="e56fc-123">Nel riquadro **Aggiungi amministratori** digitare il nome visualizzato o il nome utente dell'utente e quindi selezionare l'utente nell'elenco dei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="e56fc-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="e56fc-124">Aggiungi più utenti finché non hai finito.</span><span class="sxs-lookup"><span data-stu-id="e56fc-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="e56fc-125">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e56fc-125">Select **Save**.</span></span> <span data-ttu-id="e56fc-126">L'utente viene aggiunto all'elenco degli amministratori assegnati.</span><span class="sxs-lookup"><span data-stu-id="e56fc-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="e56fc-127">Rimuovere i ruoli di amministratore tramite la pagina Notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="e56fc-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="e56fc-128">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="e56fc-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="e56fc-129">Nella sezione **Amministratori che ricevono notifiche di fatturazione** selezionare il collegamento Amministratore fatturazione o **Amministratore** globale nel testo della descrizione. </span><span class="sxs-lookup"><span data-stu-id="e56fc-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="e56fc-130">Nel riquadro destro, nella **scheda Amministratori assegnati,** selezionare gli utenti da rimuovere dal ruolo e quindi selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="e56fc-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="e56fc-131">Nella casella di conferma selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="e56fc-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="e56fc-132">L'utente viene rimosso dall'elenco degli amministratori assegnati.</span><span class="sxs-lookup"><span data-stu-id="e56fc-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="e56fc-133">Modificare gli indirizzi di posta elettronica per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="e56fc-133">Change the email addresses for admins</span></span>

<span data-ttu-id="e56fc-134">Per modificare l'indirizzo di posta elettronica primario e alternativo di altri amministratori dell'organizzazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e56fc-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="e56fc-135">Gli amministratori della fatturazione possono modificare i propri indirizzi di posta elettronica principali e alternativi, ma non per altri amministratori.</span><span class="sxs-lookup"><span data-stu-id="e56fc-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="e56fc-136">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="e56fc-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="e56fc-137">Nella sezione **Amministratori che ricevono notifiche di fatturazione** seleziona un nome.</span><span class="sxs-lookup"><span data-stu-id="e56fc-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="e56fc-138">Nel riquadro destro aggiungere o aggiornare l'indirizzo di posta elettronica primario e alternativo in base alle esigenze, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e56fc-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="e56fc-139">Modificare il messaggio di posta elettronica di contatto dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e56fc-139">Change your organization's contact email</span></span>

<span data-ttu-id="e56fc-140">Oltre agli amministratori globali e di fatturazione, microsoft invia notifiche di fatturazione all'indirizzo di posta elettronica di contatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e56fc-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="e56fc-141">Per modificare l'indirizzo di posta elettronica, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e56fc-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="e56fc-142">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="e56fc-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="e56fc-143">In **Contatto dell'organizzazione che riceve le notifiche di fatturazione** selezionare il contatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e56fc-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="e56fc-144">Nel riquadro destro digitare l'indirizzo di posta elettronica che si desidera utilizzare, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e56fc-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="e56fc-145">Ricevere le fatture dell'organizzazione come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="e56fc-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="e56fc-146">Gli amministratori della fatturazione possono anche eseguire la procedura descritta in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e56fc-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="e56fc-147">È possibile allegare una copia della fattura dell'organizzazione come file PDF ai messaggi di posta elettronica di notifica delle fatture quando è pronta una nuova fattura.</span><span class="sxs-lookup"><span data-stu-id="e56fc-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="e56fc-148">Per ricevere le fatture come allegati, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e56fc-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="e56fc-149">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="e56fc-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="e56fc-150">In **Impostazioni notifiche di fatturazione** selezionare Modifica impostazioni **notifica.**</span><span class="sxs-lookup"><span data-stu-id="e56fc-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="e56fc-151">Nel riquadro **Impostazioni notifica fatturazione,** in **Allega un PDF** ai messaggi di posta elettronica della fattura, seleziona la casella di controllo, quindi seleziona **Salva.**</span><span class="sxs-lookup"><span data-stu-id="e56fc-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="e56fc-152">Per interrompere la ricezione **dell'allegato** della fattura in qualsiasi momento, seguire i passaggi precedenti e deselezionare la casella di controllo Allega un PDF ai messaggi di posta elettronica della fattura nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e56fc-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="e56fc-153">Cosa succede se si dispone di un profilo di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="e56fc-153">What if I have a billing profile?</span></span>

<span data-ttu-id="e56fc-154">Se si dispone di un profilo di fatturazione, alcuni dei passaggi descritti in questo articolo potrebbero essere leggermente diversi per alcuni abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="e56fc-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="e56fc-155">In questa sezione vengono descritte queste differenze.</span><span class="sxs-lookup"><span data-stu-id="e56fc-155">This section describes those differences.</span></span> [<span data-ttu-id="e56fc-156">Come è possibile sapere se si dispone di un profilo di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="e56fc-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="e56fc-157">Who riceve le notifiche di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="e56fc-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="e56fc-158">I messaggi di posta elettronica di notifica di fatturazione vengono inviati agli indirizzi di posta elettronica principali e alternativi per gli utenti a cui è assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e56fc-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="e56fc-159">Proprietario del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="e56fc-159">Billing profile owner</span></span>
- <span data-ttu-id="e56fc-160">Collaboratore del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="e56fc-160">Billing profile contributor</span></span>
- <span data-ttu-id="e56fc-161">Responsabile delle fatture</span><span class="sxs-lookup"><span data-stu-id="e56fc-161">Invoice manager</span></span>

<span data-ttu-id="e56fc-162">Per ulteriori informazioni sui ruoli del profilo di fatturazione e su come gestirli, vedere Informazioni sui ruoli amministrativi del Contratto con i clienti [Microsoft in Azure.](/azure/cost-management-billing/manage/understand-mca-roles)</span><span class="sxs-lookup"><span data-stu-id="e56fc-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="e56fc-163">Per modificare chi riceve le notifiche di fatturazione dell'organizzazione, eseguire la procedura seguente per modificare i ruoli assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e56fc-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="e56fc-164">Nell'interfaccia di amministrazione passare alla **pagina Fatturazione**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamenti.</a></span><span class="sxs-lookup"><span data-stu-id="e56fc-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="e56fc-165">Nella scheda **Profilo di fatturazione** selezionare un profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="e56fc-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="e56fc-166">Nella sezione **Ruoli profilo di fatturazione** assegnare o rimuovere ruoli per Proprietario profilo di fatturazione, **Collaboratore** profilo di fatturazione o **Responsabile fatture.** </span><span class="sxs-lookup"><span data-stu-id="e56fc-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="e56fc-167">Ricevere fatture come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="e56fc-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="e56fc-168">Per ricevere le fatture come allegati alle notifiche delle fatture, eseguire la procedura seguente per attivare questa impostazione per un profilo di fatturazione specifico.</span><span class="sxs-lookup"><span data-stu-id="e56fc-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="e56fc-169">Nell'interfaccia di amministrazione passare alla **pagina Fatturazione**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamenti.</a></span><span class="sxs-lookup"><span data-stu-id="e56fc-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="e56fc-170">Seleziona la **scheda Profili di** fatturazione, quindi seleziona un profilo di fatturazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="e56fc-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="e56fc-171">Nella pagina dei dettagli del profilo di fatturazione, in Ottieni fatture negli allegati di posta **elettronica,** impostare l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="e56fc-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="e56fc-172">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="e56fc-172">Related content</span></span>

<span data-ttu-id="e56fc-173">[Visualizzare l'estratto conto o la fattura](view-your-bill-or-invoice.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="e56fc-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="e56fc-174">[Comprendere la fattura o la fattura per Microsoft 365 per le aziende](understand-your-invoice2.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="e56fc-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="e56fc-175">[Aggiungere utenti e assegnare licenze contemporaneamente](../../admin/add-users/add-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="e56fc-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
