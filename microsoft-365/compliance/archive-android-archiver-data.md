---
title: Configurare un connettore per l'archiviazione dei dati per dispositivi mobili Android
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore di invio di messaggi per importare e archiviare SMS, MMS e chiamate vocali dai telefoni cellulari Android. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, come la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 0eb8d77abb0c18abead03cb744102e795b7a57b5
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282624"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data-preview"></a><span data-ttu-id="03607-104">Configurare un connettore per l'archiviazione dei dati per dispositivi mobili Android (anteprima)</span><span class="sxs-lookup"><span data-stu-id="03607-104">Set up a connector to archive Android mobile data (preview)</span></span>

<span data-ttu-id="03607-105">Utilizzare un connettore TeleMessage nel centro conformità di Microsoft 365 per importare e archiviare SMS, MMS, chiamate vocali e registri di chiamata dai telefoni cellulari Android.</span><span class="sxs-lookup"><span data-stu-id="03607-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive SMS, MMS, voice calls, and call logs from Android mobile phones.</span></span> <span data-ttu-id="03607-106">Dopo aver configurato e configurato un connettore, si connette all'account del telemessaggio dell'organizzazione una volta al giorno e importa la comunicazione mobile dei dipendenti utilizzando l'archiviatore Android di telemessaggio per le cassette postali in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03607-106">After you set up and configure a connector, it connects to your organization's TeleMessage account once every day, and imports the mobile communication of employees using the TeleMessage Android Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="03607-107">Dopo che i dati dei telefoni cellulari Android sono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio i criteri di conservazione per controversia legale, ricerca contenuto e Microsoft 365, per i dati di archiviazione Android.</span><span class="sxs-lookup"><span data-stu-id="03607-107">After data from Android mobile phones is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to Android Archiver data.</span></span> <span data-ttu-id="03607-108">Ad esempio, è possibile cercare la comunicazione mobile di Android Archiver utilizzando la ricerca contenuto o associare la cassetta postale contenente i dati del connettore di archiviazione Android con un custode in un caso avanzato di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="03607-108">For example, you can search Android Archiver mobile communication using Content Search or associate the mailbox that contains the Android Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="03607-109">L'utilizzo di un connettore di archiviazione Android per l'importazione e l'archiviazione dei dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.</span><span class="sxs-lookup"><span data-stu-id="03607-109">Using an Android Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-android-mobile-data"></a><span data-ttu-id="03607-110">Panoramica dell'archiviazione dei dati per dispositivi mobili Android</span><span class="sxs-lookup"><span data-stu-id="03607-110">Overview of archiving Android mobile data</span></span>

<span data-ttu-id="03607-111">Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per l'archiviazione dei dati per dispositivi mobili Android in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03607-111">The following overview explains the process of using a connector to archive Android mobile data in Microsoft 365.</span></span>

![Flusso di lavoro del connettore del Archiver Android](../media/AndroidArchiverConnectorWorkflow.png)

1. <span data-ttu-id="03607-113">L'organizzazione collabora con TeleMessage per configurare un connettore di archiviazione Android.</span><span class="sxs-lookup"><span data-stu-id="03607-113">Your organization works with TeleMessage to set up an Android Archiver connector.</span></span> <span data-ttu-id="03607-114">Per ulteriori informazioni, vedere [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).</span><span class="sxs-lookup"><span data-stu-id="03607-114">For more information, see [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).</span></span>

2. <span data-ttu-id="03607-115">Una volta ogni 24 ore, SMS, MMS, chiamate vocali e registri di chiamata provenienti dai telefoni cellulari Android dell'organizzazione vengono copiati nel sito di telemessaggio.</span><span class="sxs-lookup"><span data-stu-id="03607-115">Once every 24 hours, SMS, MMS, voice calls, and call logs from your organization's Android mobile phones are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="03607-116">Il connettore di archiviazione Android creato nel centro conformità di Microsoft 365 si connette al sito di telemessaggio ogni giorno e trasferisce i dati Android dalle 24 ore precedenti in una posizione di memoria di Azure sicura nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03607-116">The Android Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the Android data from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="03607-117">Il connettore converte i dati Android anche in un formato di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="03607-117">The connector also converts the Android data to an email message format.</span></span>

4. <span data-ttu-id="03607-118">Il connettore importa gli elementi di comunicazione per dispositivi mobili sulla cassetta postale di un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="03607-118">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="03607-119">Verrà creata una nuova cartella denominata Android Archiver nella cassetta postale dell'utente specifico e gli elementi verranno importati.</span><span class="sxs-lookup"><span data-stu-id="03607-119">A new folder named Android Archiver will be created in the specific user's mailbox and the items will be imported to it.</span></span> <span data-ttu-id="03607-120">Il connettore esegue il mapping utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* .</span><span class="sxs-lookup"><span data-stu-id="03607-120">The connector does mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="03607-121">Ogni messaggio di posta elettronica contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="03607-121">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="03607-122">Oltre a eseguire il mapping automatico degli utenti utilizzando il valore della proprietà dell' *indirizzo di posta elettronica dell'utente* , è anche possibile definire un mapping personalizzato caricando un file di mapping CSV.</span><span class="sxs-lookup"><span data-stu-id="03607-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="03607-123">Questo file di mapping deve contenere il numero di cellulare dell'utente e l'indirizzo della cassetta postale di Microsoft 365 corrispondente per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="03607-123">This mapping file should contain User’s mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="03607-124">Se si Abilita il mapping automatico degli utenti e si fornisce un mapping personalizzato, per ogni elemento di posta elettronica il connettore osserverà per la prima volta il file di mapping personalizzato.</span><span class="sxs-lookup"><span data-stu-id="03607-124">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="03607-125">Se non trova un utente valido di Microsoft 365 che corrisponde al numero di cellulare di un utente, il connettore utilizzerà la proprietà dell'indirizzo di posta elettronica dell'utente dell'elemento di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="03607-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="03607-126">Se il connettore non trova un utente valido di Microsoft 365 nel file di mapping personalizzato o nella proprietà dell' *indirizzo di posta elettronica dell'utente* dell'elemento di posta elettronica, l'elemento non verrà importato.</span><span class="sxs-lookup"><span data-stu-id="03607-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user’s email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="03607-127">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="03607-127">Before you begin</span></span>

<span data-ttu-id="03607-128">Molti dei passaggi di implementazione necessari per archiviare i dati di comunicazione Android sono esterni a Microsoft 365 e devono essere completati prima di poter creare il connettore nel centro conformità.</span><span class="sxs-lookup"><span data-stu-id="03607-128">Many of the implementation steps required to archive Android communication data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="03607-129">Ordinare il [servizio di archiviazione Android da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e ottenere un account di amministrazione valido per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03607-129">Order the [Android Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="03607-130">Sarà necessario accedere a questo account quando si crea il connettore.</span><span class="sxs-lookup"><span data-stu-id="03607-130">You'll need to sign into this account when you create the connector.</span></span>

- <span data-ttu-id="03607-131">Registrare tutti gli utenti che richiedono il servizio di archiviazione Android nell'account TeleMessage.</span><span class="sxs-lookup"><span data-stu-id="03607-131">Register all users that require the Android Archiver service in the TeleMessage account.</span></span> <span data-ttu-id="03607-132">Quando si registrano gli utenti, assicurarsi di utilizzare lo stesso indirizzo di posta elettronica utilizzato per il proprio account Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03607-132">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="03607-133">Installare e attivare l'applicazione TeleMessage Android Archiver sui telefoni cellulari dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="03607-133">Install and activate the TeleMessage Android Archiver app on the mobile phones of your employees.</span></span>

- <span data-ttu-id="03607-134">L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03607-134">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="03607-135">Sarà necessario fornire questo consenso quando si crea il connettore.</span><span class="sxs-lookup"><span data-stu-id="03607-135">You will need to provide this consent when you create the connector.</span></span> <span data-ttu-id="03607-136">Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="03607-136">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span> <span data-ttu-id="03607-137">È necessario completare questo passaggio prima di poter creare correttamente un connettore di rete di&T.</span><span class="sxs-lookup"><span data-stu-id="03607-137">You have to complete this step before you can successfully create an AT&T Network connector.</span></span>

- <span data-ttu-id="03607-138">All'utente che crea un connettore di archiviazione Android deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="03607-138">The user who creates a Android Archiver connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="03607-139">Questa operazione è necessaria per aggiungere connettori nella pagina **connettori dati** del centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03607-139">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="03607-140">Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="03607-140">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="03607-141">È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="03607-141">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="03607-142">In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri.</span><span class="sxs-lookup"><span data-stu-id="03607-142">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="03607-143">Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="03607-143">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-an-android-archiver-connector"></a><span data-ttu-id="03607-144">Creare un connettore di archiviazione Android</span><span class="sxs-lookup"><span data-stu-id="03607-144">Create an Android Archiver connector</span></span>

<span data-ttu-id="03607-145">L'ultimo passaggio consiste nel creare un connettore di archiviazione Android nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03607-145">The last step is to create an Android Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="03607-146">Il connettore utilizza le informazioni fornite per la connessione al sito di telemessaggio e trasferisce la comunicazione Android nelle caselle della cassetta postale dell'utente corrispondente in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03607-146">The connector uses the information you provide to connect to the TeleMessage site and transfer Android communication to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="03607-147">Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **Data Connectors**  >  **Android Archiver**.</span><span class="sxs-lookup"><span data-stu-id="03607-147">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** > **Android Archiver**.</span></span>

2. <span data-ttu-id="03607-148">Nella pagina Descrizione prodotto di **Android Archiver** fare clic su **Aggiungi connettore**.</span><span class="sxs-lookup"><span data-stu-id="03607-148">On the **Android Archiver** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="03607-149">Nella pagina **condizioni del servizio** fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="03607-149">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="03607-150">Nella pagina **accesso a telemessaggio** , in passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="03607-150">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="03607-151">**Nome utente:** Nome utente del telemessaggio.</span><span class="sxs-lookup"><span data-stu-id="03607-151">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="03607-152">**Password:** La password del telemessaggio.</span><span class="sxs-lookup"><span data-stu-id="03607-152">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="03607-153">Dopo aver creato il connettore, chiudere la finestra popup e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="03607-153">After the connector is created, close the pop-up window and click **Next**.</span></span>

6. <span data-ttu-id="03607-154">Nella pagina **mapping utenti** abilitare il mapping automatico degli utenti e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="03607-154">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="03607-155">Nel caso in cui sia necessario un mapping personalizzato caricare un file CSV e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="03607-155">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="03607-156">Fornire il consenso dell'amministratore e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="03607-156">Provide admin consent and then click **Next**.</span></span>

   <span data-ttu-id="03607-157">Per fornire il consenso dell'amministratore, è necessario essere connessi con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta di consenso.</span><span class="sxs-lookup"><span data-stu-id="03607-157">To provide admin consent, you must be signed in with the credentials of an Office 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="03607-158">Se non è stato eseguito l'accesso come amministratore globale, è possibile accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e accedere usando le credenziali di amministratore globale per accettare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="03607-158">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign-in using global admin credentials to accept the request.</span></span>

8. <span data-ttu-id="03607-159">Esaminare le impostazioni e quindi fare clic su **fine** per creare il connettore.</span><span class="sxs-lookup"><span data-stu-id="03607-159">Review your settings, and then click **Finish** to create the connector.</span></span>

9. <span data-ttu-id="03607-160">Passare alla scheda Connettori della pagina **connettori dati** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.</span><span class="sxs-lookup"><span data-stu-id="03607-160">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="03607-161">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="03607-161">Known issues</span></span>

- <span data-ttu-id="03607-162">Il connettore non importa alcun elemento di dimensioni superiori a 10 MB.</span><span class="sxs-lookup"><span data-stu-id="03607-162">The connector doesn’t import any item larger than 10 MB.</span></span>