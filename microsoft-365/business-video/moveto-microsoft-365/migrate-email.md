---
title: Eseguire la migrazione della posta elettronica aziendale e del calendario da Google Workspace
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come eseguire la migrazione di posta elettronica, contatti e calendario da Google Workspace a Microsoft 365 per le aziende.
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928247"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="b2458-103">Eseguire la migrazione della posta elettronica aziendale e del calendario da Google Workspace</span><span class="sxs-lookup"><span data-stu-id="b2458-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="b2458-104">È possibile utilizzare una migrazione eseguita dall'amministratore a Exchange Online da Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="b2458-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="b2458-105">È possibile eseguire la migrazione della posta in una sola volta o in più fasi.</span><span class="sxs-lookup"><span data-stu-id="b2458-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="b2458-106">La procedura seguente mostra come eseguire la migrazione dei dati di posta elettronica contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b2458-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="b2458-107">Per ulteriori informazioni, vedere [Eseguire una migrazione G Suite.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="b2458-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="b2458-108">Il processo di migrazione richiede diversi passaggi e può richiedere da diverse ore a un paio di giorni a seconda della quantità di dati di cui si esegue la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b2458-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="b2458-109">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="b2458-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="b2458-110">Creare un account di servizio Google</span><span class="sxs-lookup"><span data-stu-id="b2458-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="b2458-111">Utilizzando un browser Chrome, accedere alla console di amministrazione di Google Workspace [all'indirizzo admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="b2458-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="b2458-112">In una nuova scheda o finestra passare alla pagina [Account di](https://console.developers.google.com/iam-admin/serviceaccounts) servizio.</span><span class="sxs-lookup"><span data-stu-id="b2458-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="b2458-113">Selezionare **Crea progetto,** assegnare un nome al progetto e scegliere **Crea.**</span><span class="sxs-lookup"><span data-stu-id="b2458-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="b2458-114">Selezionare **Crea account del servizio,** immettere un nome, scegliere **Crea** e quindi **Fine.**</span><span class="sxs-lookup"><span data-stu-id="b2458-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="b2458-115">Aprire il menu **Azioni,** selezionare **Modifica** e prendere nota dell'ID univoco.</span><span class="sxs-lookup"><span data-stu-id="b2458-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="b2458-116">Questo ID sarà necessario più avanti nel processo.</span><span class="sxs-lookup"><span data-stu-id="b2458-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="b2458-117">Aprire la **sezione Mostra delega a livello di** dominio.</span><span class="sxs-lookup"><span data-stu-id="b2458-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="b2458-118">Seleziona Abilita delega a livello di **dominio G Suite,** immetti un nome di prodotto per la schermata di consenso e scegli **Salva.**</span><span class="sxs-lookup"><span data-stu-id="b2458-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="b2458-119">Il nome del prodotto non viene utilizzato dal processo di migrazione, ma è necessario per salvare nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b2458-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="b2458-120">Apri di **nuovo il** menu Azioni e seleziona **Crea chiave.**</span><span class="sxs-lookup"><span data-stu-id="b2458-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="b2458-121">Scegliere **JSON,** quindi **Crea.**</span><span class="sxs-lookup"><span data-stu-id="b2458-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="b2458-122">La chiave privata viene salvata nella cartella di download del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b2458-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="b2458-123">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b2458-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="b2458-124">Abilitare l'utilizzo dell'API per il progetto</span><span class="sxs-lookup"><span data-stu-id="b2458-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="b2458-125">Passa alla [pagina DELLE API.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="b2458-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="b2458-126">Nella barra di ricerca, immettere **Gmail API.**</span><span class="sxs-lookup"><span data-stu-id="b2458-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="b2458-127">Selezionarlo e quindi scegliere **Abilita.**</span><span class="sxs-lookup"><span data-stu-id="b2458-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="b2458-128">Ripeti questo processo per l'API Google Calendar e l'API Contatti.</span><span class="sxs-lookup"><span data-stu-id="b2458-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="b2458-129">Concedere l'accesso all'account del servizio</span><span class="sxs-lookup"><span data-stu-id="b2458-129">Grant access to the service account</span></span>

1. <span data-ttu-id="b2458-130">Torna alla console di amministrazione di Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="b2458-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="b2458-131">Seleziona **Sicurezza,** scorri verso il basso e apri i **controlli api.**</span><span class="sxs-lookup"><span data-stu-id="b2458-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="b2458-132">Scorrere verso il basso e **selezionare Gestisci delega a livello di dominio.**</span><span class="sxs-lookup"><span data-stu-id="b2458-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="b2458-133">Seleziona **Aggiungi nuovo** e immetti l'ID client di cui hai preso nota in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b2458-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="b2458-134">Immettere quindi gli ambiti OAuth per le API Di Google.</span><span class="sxs-lookup"><span data-stu-id="b2458-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="b2458-135">Questi sono disponibili al [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) passaggio 5 e sono:</span><span class="sxs-lookup"><span data-stu-id="b2458-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="b2458-136">Scegliere **Autorizza.**</span><span class="sxs-lookup"><span data-stu-id="b2458-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="b2458-137">Creare un sottodominio per la posta in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b2458-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="b2458-138">Torna alla **console di amministrazione di Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="b2458-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="b2458-139">Selezionare **Domini**, **Gestisci domini**, quindi Aggiungere un alias di **dominio.**</span><span class="sxs-lookup"><span data-stu-id="b2458-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="b2458-140">Immettere un alias di dominio come `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="b2458-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="b2458-141">Selezionare Continua **e verificare la proprietà del dominio.**</span><span class="sxs-lookup"><span data-stu-id="b2458-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="b2458-142">La verifica del dominio in genere richiede pochi minuti, ma può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="b2458-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="b2458-143">Passare all'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b2458-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="b2458-144">Nell'interfaccia di amministrazione di **Microsoft 365,** nel riquadro di spostamento sinistro, selezionare **Mostra** tutto, **Impostazioni**, **Domini** e quindi **Aggiungi dominio.**</span><span class="sxs-lookup"><span data-stu-id="b2458-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="b2458-145">Immettere il sottodominio creato in precedenza, quindi selezionare **Usa questo dominio.**</span><span class="sxs-lookup"><span data-stu-id="b2458-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="b2458-146">Per connettere il dominio, selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="b2458-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="b2458-147">Scorrere verso il basso e prendere nota dei record MX, CNAME e TXT.</span><span class="sxs-lookup"><span data-stu-id="b2458-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="b2458-148">Torna alla **console di amministrazione di Google.**</span><span class="sxs-lookup"><span data-stu-id="b2458-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="b2458-149">Selezionare **Domini,** selezionare **Gestisci domini,** **Verifica dettagli** e quindi **Gestisci dominio.**</span><span class="sxs-lookup"><span data-stu-id="b2458-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="b2458-150">Nel riquadro di spostamento sinistro scegliere **DNS** e scorrere verso il basso fino **a Record di risorse personalizzati.**</span><span class="sxs-lookup"><span data-stu-id="b2458-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="b2458-151">Aprire l'elenco a discesa del tipo di record e selezionare **MX,** immettere o copiare e incollare le informazioni sul record MX precedentemente specificate, quindi scegliere **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="b2458-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="b2458-152">Ripetere il processo per il record CNAME e il record TXT.</span><span class="sxs-lookup"><span data-stu-id="b2458-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="b2458-153">L'applicazione di queste modifiche potrebbe richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="b2458-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="b2458-154">Tornare al punto in cui è stato lasciato l'interfaccia di amministrazione di **Microsoft 365** e selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="b2458-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="b2458-155">Il dominio è ora configurato.</span><span class="sxs-lookup"><span data-stu-id="b2458-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="b2458-156">Creare alias di posta elettronica in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b2458-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="b2458-157">Prima di iniziare la migrazione, è necessario creare alias di posta elettronica per gli utenti con il nuovo sottodominio.</span><span class="sxs-lookup"><span data-stu-id="b2458-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="b2458-158">Per avviare il passaggio successivo, nella **procedura** guidata Aggiungi domini nell'interfaccia di amministrazione di Microsoft 365 selezionare Vai agli **utenti attivi.**</span><span class="sxs-lookup"><span data-stu-id="b2458-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="b2458-159">Seleziona un utente, quindi Gestisci nome **utente e posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="b2458-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="b2458-160">**Nell'elenco a** discesa Domini selezionare il sottodominio creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b2458-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="b2458-161">Immetti un nome utente, seleziona **Aggiungi,** **Salva modifiche** e chiudi la finestra.</span><span class="sxs-lookup"><span data-stu-id="b2458-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="b2458-162">Ripetere questo processo per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="b2458-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="b2458-163">Avviare il processo di migrazione</span><span class="sxs-lookup"><span data-stu-id="b2458-163">Start the migration process</span></span>

<span data-ttu-id="b2458-164">Al termine, è possibile eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b2458-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="b2458-165">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di **Microsoft 365,** scorrere verso il basso fino a **Interfaccia di amministrazione** e selezionare **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="b2458-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="b2458-166">In **destinatari,** scegliere **migrazione,** selezionare **Nuovo,** **Esegui migrazione a Exchange Online,** scegliere Migrazione G **Suite** e quindi **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="b2458-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="b2458-167">Creare un file CSV con un elenco delle cassette postali di cui si desidera eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="b2458-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="b2458-168">Verificare che il file sia in questo formato:</span><span class="sxs-lookup"><span data-stu-id="b2458-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="b2458-169">Per informazioni dettagliate, [vedere aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="b2458-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="b2458-170">Seleziona **Scegli file,** passa al file CSV, sceglilo, seleziona **Apri** e quindi **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="b2458-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="b2458-171">Verificare l'indirizzo di posta elettronica dell'amministratore che si desidera utilizzare per i test.</span><span class="sxs-lookup"><span data-stu-id="b2458-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="b2458-172">Seleziona **Scegli file,** passa al file JSON creato in precedenza (in genere nella cartella Download nel computer), sceglilo, seleziona **Apri** e quindi **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="b2458-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="b2458-173">Immettere un nome nel campo **Nuovo nome batch di migrazione.**</span><span class="sxs-lookup"><span data-stu-id="b2458-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="b2458-174">Immettere il sottodominio creato nel campo **Dominio di recapito di** destinazione, selezionare **Avanti** e quindi **Nuovo.**</span><span class="sxs-lookup"><span data-stu-id="b2458-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="b2458-175">Dopo aver salvato le informazioni, selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="b2458-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="b2458-176">È ora possibile visualizzare lo stato della migrazione.</span><span class="sxs-lookup"><span data-stu-id="b2458-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="b2458-177">Dopo un certo periodo di tempo, a seconda del numero di utenti di cui si sta eseguendo la migrazione, selezionare **Aggiorna.**</span><span class="sxs-lookup"><span data-stu-id="b2458-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="b2458-178">Dopo aver modificato lo stato in **Sincronizzato,** selezionare **Completa il batch di migrazione,** quindi **Sì.**</span><span class="sxs-lookup"><span data-stu-id="b2458-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="b2458-179">Una volta completato il processo, lo stato cambierà in **Completato.**</span><span class="sxs-lookup"><span data-stu-id="b2458-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="b2458-180">Se si desidera, è possibile selezionare **Visualizza dettagli** per ulteriori informazioni sulla migrazione.</span><span class="sxs-lookup"><span data-stu-id="b2458-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="b2458-181">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b2458-181">Select **Close**.</span></span> 
1. <span data-ttu-id="b2458-182">Aprire Outlook per verificare che la migrazione di tutti i messaggi di posta elettronica da Google Workspace sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b2458-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="b2458-183">È possibile ripetere questa operazione anche per gli elementi del calendario e i contatti.</span><span class="sxs-lookup"><span data-stu-id="b2458-183">You can repeat this for calendar items and contacts as well.</span></span>