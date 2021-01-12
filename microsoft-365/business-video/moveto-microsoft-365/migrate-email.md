---
title: Eseguire la migrazione della posta elettronica e del calendario aziendale da Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come eseguire la migrazione di posta elettronica, contatti e calendario da Google Workspace a Microsoft 365 for business.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794646"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="da3f6-103">Eseguire la migrazione della posta elettronica e del calendario aziendale da Google Workspace</span><span class="sxs-lookup"><span data-stu-id="da3f6-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="da3f6-104">È possibile utilizzare una migrazione con l'amministratore eseguito a Exchange Online da Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="da3f6-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="da3f6-105">È possibile eseguire la migrazione della posta elettronica in una sola volta o in fasi.</span><span class="sxs-lookup"><span data-stu-id="da3f6-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="da3f6-106">Nei passaggi seguenti viene illustrato come eseguire la migrazione dei dati di posta elettronica in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="da3f6-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="da3f6-107">Per ulteriori informazioni, vedere [eseguire la migrazione di un gruppo G](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span><span class="sxs-lookup"><span data-stu-id="da3f6-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="da3f6-108">Il processo di migrazione richiede diversi passaggi e può richiedere da diverse ore a un paio di giorni a seconda della quantità di dati di cui si esegue la migrazione.</span><span class="sxs-lookup"><span data-stu-id="da3f6-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="da3f6-109">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="da3f6-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="da3f6-110">Creare un account di servizio di Google</span><span class="sxs-lookup"><span data-stu-id="da3f6-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="da3f6-111">Utilizzando un browser Chrome, accedere alla console di amministrazione di Google Workspace all' [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="da3f6-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="da3f6-112">In una nuova scheda o finestra passare alla pagina [account di servizio](https://console.developers.google.com/iam-admin/serviceaccounts) .</span><span class="sxs-lookup"><span data-stu-id="da3f6-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="da3f6-113">Selezionare **Crea progetto**, denominare il progetto e scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="da3f6-114">Selezionare **Crea account di servizio**, immettere un nome, fare clic su **Crea** e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="da3f6-115">Aprire il menu **azioni** , selezionare **modifica** e prendere nota dell'ID univoco.</span><span class="sxs-lookup"><span data-stu-id="da3f6-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="da3f6-116">Questo ID sarà necessario in un secondo momento nel processo.</span><span class="sxs-lookup"><span data-stu-id="da3f6-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="da3f6-117">Aprire la sezione **Mostra delega a livello di dominio** .</span><span class="sxs-lookup"><span data-stu-id="da3f6-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="da3f6-118">Selezionare **Abilita delega a livello di dominio G Suite**, immettere un nome di prodotto per la schermata di consenso e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="da3f6-119">Il nome del prodotto non viene utilizzato dal processo di migrazione, ma è necessario salvarlo nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="da3f6-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="da3f6-120">Aprire di nuovo il menu **azioni** e selezionare **Crea chiave**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="da3f6-121">Scegliere **JSON** e quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="da3f6-122">La chiave privata viene salvata nella cartella di download del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="da3f6-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="da3f6-123">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="da3f6-124">Abilitazione dell'utilizzo delle API per il progetto</span><span class="sxs-lookup"><span data-stu-id="da3f6-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="da3f6-125">Passare alla [pagina Apis](https://console.developers.google.com/apis/library).</span><span class="sxs-lookup"><span data-stu-id="da3f6-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="da3f6-126">Nella barra di ricerca, immettere **Gmail API**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="da3f6-127">Selezionarlo e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="da3f6-128">Ripetere questa procedura per API di Google Calendar e API dei contatti.</span><span class="sxs-lookup"><span data-stu-id="da3f6-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="da3f6-129">Concedere l'accesso all'account di servizio</span><span class="sxs-lookup"><span data-stu-id="da3f6-129">Grant access to the service account</span></span>

1. <span data-ttu-id="da3f6-130">Tornare alla console di amministrazione di Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="da3f6-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="da3f6-131">Selezionare **sicurezza**, scorrere verso il basso e aprire i **Controlli API**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="da3f6-132">Scorrere verso il basso e selezionare **Gestisci delega a livello di dominio**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="da3f6-133">Selezionare **Aggiungi nuovo** e immettere l'ID client annotato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="da3f6-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="da3f6-134">Immettere quindi gli ambiti OAuth per le API di Google.</span><span class="sxs-lookup"><span data-stu-id="da3f6-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="da3f6-135">Sono disponibili in [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) nel passaggio 5 e sono:</span><span class="sxs-lookup"><span data-stu-id="da3f6-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="da3f6-136">Scegliere **autorizza**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="da3f6-137">Creare un sottodominio per la posta elettronica in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da3f6-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="da3f6-138">Tornare alla console di **amministrazione di Google Workspace** .</span><span class="sxs-lookup"><span data-stu-id="da3f6-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="da3f6-139">Selezionare **domini**, **Manage** Domains e quindi **aggiungere un alias di dominio**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="da3f6-140">Immettere un alias di dominio come `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="da3f6-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="da3f6-141">Quindi **, selezionare continua e verificare la proprietà del dominio**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="da3f6-142">La verifica del dominio richiede solitamente solo pochi minuti, ma può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="da3f6-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="da3f6-143">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="da3f6-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="da3f6-144">Nell'interfaccia **di amministrazione di Microsoft 365**, nella barra di spostamento sinistra, selezionare **Mostra tutto**, **Impostazioni**, **domini** e quindi **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="da3f6-145">Immettere il sottodominio creato in precedenza, quindi selezionare **Usa questo dominio**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="da3f6-146">Per connettere il dominio, selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="da3f6-147">Scorrere verso il basso e prendere nota dei record MX, record CNAME e TXT.</span><span class="sxs-lookup"><span data-stu-id="da3f6-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="da3f6-148">Tornare alla **console di amministrazione di Google**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="da3f6-149">Selezionare **domini**, selezionare **Manage** Domains, **Verify Details** e then, **Manage Domain**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="da3f6-150">Nel NAV sinistro, scegliere **DNS** e scorrere verso il basso fino a **record di risorse personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="da3f6-151">Aprire la casella di riepilogo a discesa tipo di record e selezionare **MX**, immettere o copiare e incollare le informazioni del record MX precedentemente note, quindi scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="da3f6-152">Ripetere il processo per il record CNAME e il record TXT.</span><span class="sxs-lookup"><span data-stu-id="da3f6-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="da3f6-153">Per rendere effettive le modifiche, potrebbe essere necessario un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="da3f6-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="da3f6-154">Tornare alla posizione in cui è stato interrotto nell'interfaccia di **amministrazione di Microsoft 365** e selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="da3f6-155">Il dominio è ora configurato.</span><span class="sxs-lookup"><span data-stu-id="da3f6-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="da3f6-156">Creare alias di posta elettronica in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da3f6-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="da3f6-157">Prima di iniziare la migrazione, è necessario creare alias di posta elettronica per gli utenti con il nuovo sottodominio.</span><span class="sxs-lookup"><span data-stu-id="da3f6-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="da3f6-158">Per avviare il passaggio successivo, nella procedura guidata **Aggiungi domini** nell'interfaccia di amministrazione di Microsoft 365 selezionare **Vai a utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="da3f6-159">Selezionare un utente, quindi **gestire il nome utente e la posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="da3f6-160">Nell'elenco a discesa **domini** selezionare il sottodominio creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="da3f6-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="da3f6-161">Immettere un nome utente, fare clic su **Aggiungi**, **salvare le modifiche** e chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="da3f6-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="da3f6-162">Ripetere questa procedura per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="da3f6-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="da3f6-163">Avviare il processo di migrazione</span><span class="sxs-lookup"><span data-stu-id="da3f6-163">Start the migration process</span></span>

<span data-ttu-id="da3f6-164">Dopo aver completato l'operazione, è possibile eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="da3f6-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="da3f6-165">Nella barra di spostamento sinistra dell'interfaccia di **amministrazione di Microsoft 365**, scorrere verso il basso fino a interfacce di **Amministrazione** e selezionare **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="da3f6-166">In **destinatari** fare clic su **migrazione**, selezionare **nuovo**, eseguire la migrazione **a Exchange Online**, scegliere **G Suite Migration** e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="da3f6-167">Creare un file CSV con un elenco delle cassette postali di cui si desidera eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="da3f6-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="da3f6-168">Verificare che il file segua il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="da3f6-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="da3f6-169">Per informazioni dettagliate, vedere [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="da3f6-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="da3f6-170">Selezionare **Scegli file**, passare al file CSV, selezionarlo, fare clic su **Apri**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="da3f6-171">Verificare l'indirizzo di posta elettronica dell'amministratore che si desidera utilizzare per il testing.</span><span class="sxs-lookup"><span data-stu-id="da3f6-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="da3f6-172">Selezionare **Scegli file**, passare al file JSON creato in precedenza (in genere nella cartella Downloads del computer), selezionarlo, selezionare **Apri** e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="da3f6-173">Immettere un nome nel **campo nuovo nome batch di migrazione**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="da3f6-174">Immettere il sottodominio creato nel campo **dominio di recapito di destinazione** , selezionare **Avanti** e quindi **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="da3f6-175">Dopo aver salvato le informazioni, seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="da3f6-176">È ora possibile visualizzare lo stato della migrazione.</span><span class="sxs-lookup"><span data-stu-id="da3f6-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="da3f6-177">Dopo un determinato periodo di tempo, a seconda del numero di utenti che si desidera eseguire la migrazione, selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="da3f6-178">Dopo che lo stato è stato modificato in **sincronizzato**, selezionare **completa il batch di migrazione**, quindi **Sì**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="da3f6-179">Al termine del processo, lo stato verrà modificato in **completato**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="da3f6-180">Se lo si desidera, è possibile selezionare **Visualizza dettagli** per ulteriori informazioni sulla migrazione.</span><span class="sxs-lookup"><span data-stu-id="da3f6-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="da3f6-181">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="da3f6-181">Select **Close**.</span></span> 
1. <span data-ttu-id="da3f6-182">Aprire Outlook per verificare che tutti i messaggi di posta elettronica provenienti da Google Workspace siano stati migrati correttamente.</span><span class="sxs-lookup"><span data-stu-id="da3f6-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="da3f6-183">È possibile ripetere questa operazione anche per gli elementi di calendario e i contatti.</span><span class="sxs-lookup"><span data-stu-id="da3f6-183">You can repeat this for calendar items and contacts as well.</span></span>