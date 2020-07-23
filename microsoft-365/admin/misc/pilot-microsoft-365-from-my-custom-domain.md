---
title: Eseguire il pilota Microsoft 365 dal dominio personalizzato
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Per informazioni su come eseguire il pilota della funzionalità di posta elettronica dal dominio personalizzato a una cassetta postale di Microsoft 365 usando solo due account di test.
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186044"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="432c9-103">Eseguire il pilota Microsoft 365 dal dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="432c9-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="432c9-104">È possibile eseguire il pilota Microsoft 365 con i requisiti e le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="432c9-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="432c9-105">Il provider di posta elettronica corrente deve supportare l'inoltro dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="432c9-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="432c9-106">È necessario gestire i record DNS di Microsoft 365 presso il proprio provider di hosting DNS, piuttosto che Microsoft 365 li gestisca per tuo conto.</span><span class="sxs-lookup"><span data-stu-id="432c9-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="432c9-107">Per altre informazioni, vedere [Aggiungere record DNS per connettere il dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="432c9-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="432c9-108">Le informazioni sulla disponibilità per gli utenti dell'altro server di posta elettronica non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="432c9-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="432c9-109">Gli amministratori non possono amministrare tutti gli account utente da un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="432c9-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="432c9-110">Gli utenti potrebbero non essere in grado di usare il filtro della posta indesiderata di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="432c9-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="432c9-111">Configurare un progetto pilota di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="432c9-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="432c9-112">Seguire i passaggi seguenti per configurare un progetto pilota di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="432c9-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="432c9-113">Passaggio 1: accedere all'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="432c9-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="432c9-114">Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) con l'account aziendale o dell’istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="432c9-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="432c9-115">Scegliere **Impostazioni** > **Domini** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="432c9-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="432c9-116">Passaggio 2: verificare di essere proprietari del dominio che si vuole usare</span><span class="sxs-lookup"><span data-stu-id="432c9-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="432c9-117">Nella pagina **Domini**, selezionare **Aggiungere un dominio**.</span><span class="sxs-lookup"><span data-stu-id="432c9-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="432c9-118">Digitare il nome di dominio nella casella, selezionare **Usare questo dominio**e quindi selezionare **Continuare**.</span><span class="sxs-lookup"><span data-stu-id="432c9-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="432c9-119">Selezionare i servizi che si desidera testare con il dominio, ad esempio la posta elettronica e la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="432c9-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="432c9-120">Nella pagina **Verifica** dominio, seguire le istruzioni dettagliate e quindi selezionare **Verificare**.</span><span class="sxs-lookup"><span data-stu-id="432c9-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="432c9-121">L'applicazione delle modifiche apportate al DNS richiede da pochi minuti a 72 ore.</span><span class="sxs-lookup"><span data-stu-id="432c9-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="432c9-122">Se la verifica riesce, verrà chiesto di modificare i record DNS.</span><span class="sxs-lookup"><span data-stu-id="432c9-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="432c9-123">Passaggio 3: Contrassegnare il dominio come condiviso in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="432c9-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="432c9-124">Nell'interfaccia di amministrazione di Exchange, nella sezione **Flusso di posta**, selezionare **Domini accettati** e quindi selezionare il dominio da modificare.</span><span class="sxs-lookup"><span data-stu-id="432c9-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="432c9-125">Fare doppio clic per aprire la finestra e quindi selezionare **Inoltro interno**.</span><span class="sxs-lookup"><span data-stu-id="432c9-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="432c9-126">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="432c9-126">Select **Save**.</span></span>

    <span data-ttu-id="432c9-127">L'applicazione di questa impostazione può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="432c9-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="432c9-128">Passaggio 4: sbloccare il server di posta elettronica esistente (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="432c9-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="432c9-129">Microsoft 365 usa Exchange Online Protection (EOP) per la protezione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="432c9-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="432c9-130">EOP potrebbe bloccare il server di posta esistente se rileva un volume elevato di posta indesiderata inviato dal server di posta corrente.</span><span class="sxs-lookup"><span data-stu-id="432c9-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="432c9-131">Se si ritiene attendibile la protezione dalla posta indesiderata per l'altro provider di posta elettronica, è possibile sbloccare il server in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="432c9-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="432c9-132">Se si sblocca il server di posta elettronica esistente, gli eventuali messaggi di posta indesiderata che giungono nel server originale verranno recapitati nelle cassette postali di Microsoft 365 e non sarà possibile valutare quanto sia efficace la prevenzione dalla posta indesiderata di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="432c9-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="432c9-133">Nel riquadro di spostamento dell'interfaccia di amministrazione di Exchange, selezionare **Protezione**, e poi **Filtro connessioni**.</span><span class="sxs-lookup"><span data-stu-id="432c9-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="432c9-134">In **Elenco indirizzi IP consentiti**, selezionare **+** e quindi aggiungere l'indirizzo IP del server della posta per il provider di posta elettronica corrente.</span><span class="sxs-lookup"><span data-stu-id="432c9-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="432c9-135">Passaggio 5: Creare gli account utente e impostare l'indirizzo primario per le risposte</span><span class="sxs-lookup"><span data-stu-id="432c9-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="432c9-136">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365, selezionare **Utenti** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="432c9-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="432c9-137">Creare due account di test aggiungendo due utenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="432c9-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="432c9-138">Per ciascun account, selezionare **+ Aggiungi un utente**e compilare le informazioni richieste, includendo il metodo di password che si desidera verificare.</span><span class="sxs-lookup"><span data-stu-id="432c9-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="432c9-139">Per assicurarsi che la posta elettronica di un utente rimanga invariata, il campo **nome utente** deve corrispondere all'indirizzo di posta elettronica corrente dell'utente.</span><span class="sxs-lookup"><span data-stu-id="432c9-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="432c9-140">Scegliere la licenza appropriata, fare clic su **Avanti**e quindi fare clic su **Completa l'aggiunta**.</span><span class="sxs-lookup"><span data-stu-id="432c9-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="432c9-141">Accanto a **Nome utente** selezionare il nome di dominio personalizzato nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="432c9-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="432c9-142">Selezionare **Crea** > **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="432c9-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="432c9-143">Passaggio 6: Aggiornare i record DNS presso il provider di hosting DNS</span><span class="sxs-lookup"><span data-stu-id="432c9-143">Step 6: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="432c9-144">Accedere al sito Web del proprio provider di hosting DNS e seguire le istruzioni in [Aggiungere i record DNS per connettere il dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="432c9-144">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="432c9-145">**Fare le seguenti due eccezioni:**</span><span class="sxs-lookup"><span data-stu-id="432c9-145">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="432c9-146">Non creare un nuovo record MX né modificare il record MX esistente.</span><span class="sxs-lookup"><span data-stu-id="432c9-146">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="432c9-147">Se si dispone già di un record SPF (Sender Policy Framework) per il provider di posta elettronica precedente, invece di creare un nuovo record SPF (TXT) per Exchange Online, aggiungere semplicemente "include:spf.protection.outlook.com" al record TXT corrente.</span><span class="sxs-lookup"><span data-stu-id="432c9-147">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="432c9-148">Ad esempio, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="432c9-148">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="432c9-149">Se non si dispone ancora di un record SPF, modificare quello consigliato da Microsoft 365 in modo da includere il dominio del provider di posta elettronica corrente e aggiungere spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="432c9-149">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="432c9-150">In questo modo vengono autorizzati i messaggi in uscita da entrambi i sistemi di posta elettronica. </span><span class="sxs-lookup"><span data-stu-id="432c9-150">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="432c9-151">Passaggio 7: Configurare l'inoltro della posta elettronica presso il provider corrente</span><span class="sxs-lookup"><span data-stu-id="432c9-151">Step 7: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="432c9-152">Presso il provider di posta elettronica corrente impostare l'inoltro per gli account di posta elettronica sul proprio dominio onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="432c9-152">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="432c9-153">Imposta l’inoltro della cassetta postale dell’utente A su usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="432c9-153">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="432c9-154">Imposta l’inoltro della cassetta postale dell’utente B su userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="432c9-154">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="432c9-155">Al termine di questo passaggio, tutti i messaggi di posta elettronica inviati a usera@yourcompany.com e userb@yourcompany.com saranno disponibili in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="432c9-155">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="432c9-156">Contattare il provider di posta elettronica corrente per l’esatta procedura di configurazione dell'inoltro della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="432c9-156">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="432c9-157">Non è necessario conservare una copia dei messaggi presso il provider di posta elettronica corrente.</span><span class="sxs-lookup"><span data-stu-id="432c9-157">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="432c9-158">La maggior parte dei provider inoltra la posta elettronica lasciando intatto l'indirizzo di risposta del mittente in modo che le risposte vengano recapitate al mittente originale.</span><span class="sxs-lookup"><span data-stu-id="432c9-158">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-8-test-mail-flow"></a><span data-ttu-id="432c9-159">Passaggio 8: Testare il flusso di posta</span><span class="sxs-lookup"><span data-stu-id="432c9-159">Step 8: Test mail flow</span></span>

1. <span data-ttu-id="432c9-160">Accedere a Outlook Web App con le credenziali dell’utente A.</span><span class="sxs-lookup"><span data-stu-id="432c9-160">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="432c9-161">Eseguire i test seguenti:</span><span class="sxs-lookup"><span data-stu-id="432c9-161">Perform these tests:</span></span>

    - <span data-ttu-id="432c9-162">Testare la posta elettronica locale di Microsoft inviando un messaggio di posta elettronica, ad esempio, all'utente B. Il messaggio viene recapitato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="432c9-162">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="432c9-163">In questo caso, il messaggio non viene instradato alla cassetta postale dell'utente B nel server originale perché la cassetta postale di Microsoft 365 è locale.</span><span class="sxs-lookup"><span data-stu-id="432c9-163">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="432c9-164">Testare la posta elettronica di un utente nel sistema di posta elettronica esistente inviando un messaggio di posta elettronica, ad esempio, all'utente C. Il messaggio viene recapitato nella cassetta postale dell'utente C nel server di posta originale.</span><span class="sxs-lookup"><span data-stu-id="432c9-164">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="432c9-165">Verificare che l'inoltro sia configurato correttamente da un account esterno o da un account di posta elettronica di un dipendente nel sistema di posta elettronica esistente.</span><span class="sxs-lookup"><span data-stu-id="432c9-165">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="432c9-166">Ad esempio, dall'account del server originale per l’account dell’utente C o di un account Hotmail, inviare un messaggio di posta elettronica all’utente A e verificare che arrivi alla cassetta postale di Microsoft 365 dell'utente A.</span><span class="sxs-lookup"><span data-stu-id="432c9-166">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-9-move-mailbox-contents"></a><span data-ttu-id="432c9-167">Passaggio 9: Spostare il contenuto delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="432c9-167">Step 9: Move mailbox contents</span></span>

<span data-ttu-id="432c9-168">Dal momento che si stanno spostando solo due utenti di test e gli utenti A e B usano Outlook, è possibile spostare la posta elettronica aprendo il precedente file .PST nel nuovo profilo di Outlook e copiando i messaggi, gli elementi del calendario, i contatti e così via.</span><span class="sxs-lookup"><span data-stu-id="432c9-168">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="432c9-169">Per altre informazioni, vedere [Importare posta elettronica, contatti e calendario da un file .pst di Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="432c9-169">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="432c9-170">Dopo l'importazione nelle posizioni appropriate nella cassetta postale di Microsoft 365, è possibile accedere agli elementi ovunque e da qualsiasi dispositivo.</span><span class="sxs-lookup"><span data-stu-id="432c9-170">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="432c9-171">Se sono coinvolte più cassette postali o se i dipendenti non usano Outlook, è possibile usare gli strumenti di migrazione disponibili nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="432c9-171">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="432c9-172">Per iniziare, passare all'interfaccia di amministrazione di Exchange e seguire le istruzioni in [eseguire la migrazione della posta elettronica da un server IMAP a cassette postali di Exchange Online. È necessario una nuova risorsa per l’articolo].</span><span class="sxs-lookup"><span data-stu-id="432c9-172">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes – we need a new article resource].</span></span>