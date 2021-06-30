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
ms.openlocfilehash: a49598cd1b361a85af8455b0aff19e11fcf96526
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203245"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="b5257-103">Gestire le notifiche di fatturazione e le fatture allegate</span><span class="sxs-lookup"><span data-stu-id="b5257-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="b5257-104">La **pagina Notifiche di** fatturazione consente di gestire chi riceve i messaggi di posta elettronica di notifica di fatturazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5257-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="b5257-105">La pagina offre anche la possibilità di ricevere le fatture [dell'organizzazione come allegati di posta elettronica.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="b5257-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b5257-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b5257-106">Before you begin</span></span>

<span data-ttu-id="b5257-107">Per eseguire la procedura descritta in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="b5257-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="b5257-108">Gli amministratori della fatturazione possono apportare alcune di queste modifiche, come indicato nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b5257-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="b5257-109">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b5257-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="b5257-110">Modificare la lingua in cui si riceve la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b5257-110">Change the language you receive email in</span></span>

<span data-ttu-id="b5257-111">I messaggi di posta elettronica di notifica di fatturazione vengono inviati nella lingua preferita dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5257-111">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="b5257-112">Per modificare la lingua preferita, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b5257-112">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="b5257-113">Nella pagina interfaccia di amministrazione di Microsoft 365 fatturazione passare alla **pagina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche fatturazione.</a></span><span class="sxs-lookup"><span data-stu-id="b5257-113">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="b5257-114">Nella sezione **Impostazioni notifiche di fatturazione** seleziona Modifica impostazioni **notifica.**</span><span class="sxs-lookup"><span data-stu-id="b5257-114">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="b5257-115">Nel riquadro **Impostazioni notifica fatturazione,** in **Lingua preferita** selezionare la lingua che si desidera utilizzare, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b5257-115">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="b5257-116">Modificare chi riceve le notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="b5257-116">Change who receives billing notifications</span></span>

<span data-ttu-id="b5257-117">Le notifiche di fatturazione dell'organizzazione vengono inviate all'indirizzo di posta elettronica principale e alternativo di ogni amministratore globale e fatturazione. Per modificare gli utenti con il ruolo di amministratore Globale o Fatturazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b5257-117">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="b5257-118">Assegnare ruoli di amministratore tramite la pagina Notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="b5257-118">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="b5257-119">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="b5257-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="b5257-120">Nella sezione **Amministratori che ricevono notifiche di fatturazione** selezionare il collegamento Amministratore fatturazione o **Amministratore** globale nel testo della descrizione. </span><span class="sxs-lookup"><span data-stu-id="b5257-120">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="b5257-121">Nel riquadro destro, nella **scheda Amministratori assegnati,** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b5257-121">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="b5257-122">Nel riquadro **Aggiungi amministratori** digitare il nome visualizzato o il nome utente dell'utente e quindi selezionare l'utente nell'elenco dei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="b5257-122">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="b5257-123">Aggiungi più utenti finché non hai finito.</span><span class="sxs-lookup"><span data-stu-id="b5257-123">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="b5257-124">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b5257-124">Select **Save**.</span></span> <span data-ttu-id="b5257-125">L'utente viene aggiunto all'elenco degli amministratori assegnati.</span><span class="sxs-lookup"><span data-stu-id="b5257-125">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="b5257-126">Rimuovere i ruoli di amministratore tramite la pagina Notifiche di fatturazione</span><span class="sxs-lookup"><span data-stu-id="b5257-126">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="b5257-127">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="b5257-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="b5257-128">Nella sezione **Amministratori che ricevono notifiche di fatturazione** selezionare il collegamento Amministratore fatturazione o **Amministratore** globale nel testo della descrizione. </span><span class="sxs-lookup"><span data-stu-id="b5257-128">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="b5257-129">Nel riquadro destro, nella **scheda Amministratori assegnati,** selezionare gli utenti da rimuovere dal ruolo e quindi selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="b5257-129">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="b5257-130">Nella casella di conferma selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="b5257-130">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="b5257-131">L'utente viene rimosso dall'elenco degli amministratori assegnati.</span><span class="sxs-lookup"><span data-stu-id="b5257-131">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="b5257-132">Modificare gli indirizzi di posta elettronica per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="b5257-132">Change the email addresses for admins</span></span>

<span data-ttu-id="b5257-133">Per modificare l'indirizzo di posta elettronica primario e alternativo di altri amministratori dell'organizzazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b5257-133">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="b5257-134">Gli amministratori della fatturazione possono modificare i propri indirizzi di posta elettronica principali e alternativi, ma non per altri amministratori.</span><span class="sxs-lookup"><span data-stu-id="b5257-134">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="b5257-135">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="b5257-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="b5257-136">Nella sezione **Amministratori che ricevono notifiche di fatturazione** seleziona un nome.</span><span class="sxs-lookup"><span data-stu-id="b5257-136">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="b5257-137">Nel riquadro destro aggiungere o aggiornare l'indirizzo di posta elettronica primario e alternativo in base alle esigenze, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b5257-137">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="b5257-138">Modificare il messaggio di posta elettronica di contatto dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b5257-138">Change your organization's contact email</span></span>

<span data-ttu-id="b5257-139">Oltre agli amministratori globali e di fatturazione, microsoft invia notifiche di fatturazione all'indirizzo di posta elettronica di contatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5257-139">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="b5257-140">Per modificare l'indirizzo di posta elettronica, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b5257-140">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="b5257-141">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="b5257-141">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="b5257-142">In **Contatto dell'organizzazione che riceve le notifiche di fatturazione** selezionare il contatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5257-142">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="b5257-143">Nel riquadro destro digitare l'indirizzo di posta elettronica che si desidera utilizzare, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b5257-143">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="b5257-144">Ricevere le fatture dell'organizzazione come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b5257-144">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="b5257-145">Gli amministratori della fatturazione possono anche eseguire la procedura descritta in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="b5257-145">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="b5257-146">È possibile allegare una copia della fattura dell'organizzazione come file PDF ai messaggi di posta elettronica di notifica delle fatture quando è pronta una nuova fattura.</span><span class="sxs-lookup"><span data-stu-id="b5257-146">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="b5257-147">Per ricevere le fatture come allegati, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b5257-147">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="b5257-148">Nell'interfaccia di amministrazione, andare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notifiche sulla fatturazione</a>.</span><span class="sxs-lookup"><span data-stu-id="b5257-148">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="b5257-149">In **Impostazioni notifiche di fatturazione** selezionare Modifica impostazioni **notifica.**</span><span class="sxs-lookup"><span data-stu-id="b5257-149">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="b5257-150">Nel riquadro **Impostazioni notifica fatturazione,** in **Allega un PDF** ai messaggi di posta elettronica della fattura, seleziona la casella di controllo, quindi seleziona **Salva.**</span><span class="sxs-lookup"><span data-stu-id="b5257-150">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="b5257-151">Per interrompere la ricezione **dell'allegato** della fattura in qualsiasi momento, seguire i passaggi precedenti e deselezionare la casella di controllo Allega un PDF ai messaggi di posta elettronica della fattura nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="b5257-151">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="b5257-152">Cosa succede se si dispone di un profilo di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="b5257-152">What if I have a billing profile?</span></span>

<span data-ttu-id="b5257-153">Se si dispone di un profilo di fatturazione, alcuni dei passaggi descritti in questo articolo potrebbero essere leggermente diversi per alcuni abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="b5257-153">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="b5257-154">In questa sezione vengono descritte queste differenze.</span><span class="sxs-lookup"><span data-stu-id="b5257-154">This section describes those differences.</span></span> [<span data-ttu-id="b5257-155">Come è possibile sapere se si dispone di un profilo di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="b5257-155">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="b5257-156">Who riceve le notifiche di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="b5257-156">Who receives Billing notifications?</span></span>

<span data-ttu-id="b5257-157">I messaggi di posta elettronica di notifica di fatturazione vengono inviati agli indirizzi di posta elettronica principali e alternativi per gli utenti a cui è assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5257-157">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="b5257-158">Proprietario del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="b5257-158">Billing profile owner</span></span>
- <span data-ttu-id="b5257-159">Collaboratore del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="b5257-159">Billing profile contributor</span></span>
- <span data-ttu-id="b5257-160">Responsabile delle fatture</span><span class="sxs-lookup"><span data-stu-id="b5257-160">Invoice manager</span></span>

<span data-ttu-id="b5257-161">Per ulteriori informazioni sui ruoli del profilo di fatturazione e su come gestirli, vedere Informazioni sui ruoli amministrativi del Contratto con i clienti [Microsoft in Azure.](/azure/cost-management-billing/manage/understand-mca-roles)</span><span class="sxs-lookup"><span data-stu-id="b5257-161">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="b5257-162">Per modificare chi riceve le notifiche di fatturazione dell'organizzazione, eseguire la procedura seguente per modificare i ruoli assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b5257-162">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="b5257-163">Nell'interfaccia di amministrazione passare alla **pagina Fatturazione**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamenti.</a></span><span class="sxs-lookup"><span data-stu-id="b5257-163">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="b5257-164">Nella scheda **Profilo di fatturazione** selezionare un profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="b5257-164">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="b5257-165">Nella sezione **Ruoli profilo di fatturazione** assegnare o rimuovere ruoli per Proprietario profilo di fatturazione, **Collaboratore** profilo di fatturazione o **Responsabile fatture.** </span><span class="sxs-lookup"><span data-stu-id="b5257-165">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="b5257-166">Ricevere fatture come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b5257-166">Receive invoices as email attachments</span></span>

<span data-ttu-id="b5257-167">Per ricevere le fatture come allegati alle notifiche delle fatture, eseguire la procedura seguente per attivare questa impostazione per un profilo di fatturazione specifico.</span><span class="sxs-lookup"><span data-stu-id="b5257-167">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="b5257-168">Nell'interfaccia di amministrazione passare alla **pagina Fatturazione**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamenti.</a></span><span class="sxs-lookup"><span data-stu-id="b5257-168">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="b5257-169">Seleziona la **scheda Profili di** fatturazione, quindi seleziona un profilo di fatturazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b5257-169">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="b5257-170">Nella pagina dei dettagli del profilo di fatturazione, in Ottieni fatture negli allegati di posta **elettronica,** impostare l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="b5257-170">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="b5257-171">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="b5257-171">Related content</span></span>

<span data-ttu-id="b5257-172">[Visualizzare l'estratto conto o la fattura](view-your-bill-or-invoice.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="b5257-172">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="b5257-173">[Informazioni di fatturazione per Microsoft 365 per le aziende in Messico](mexico-billing-info.md) (articolo) </span><span class="sxs-lookup"><span data-stu-id="b5257-173">[Billing information for Microsoft 365 for business in Mexico](mexico-billing-info.md) (article) </span></span>\
<span data-ttu-id="b5257-174">[Comprendere la fattura o la fattura per Microsoft 365 per le aziende](understand-your-invoice2.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="b5257-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="b5257-175">[Aggiungere utenti e assegnare licenze contemporaneamente](../../admin/add-users/add-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="b5257-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
