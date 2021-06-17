---
title: Configurare l'hub eventi
description: Informazioni su come configurare l'hub eventi
keywords: hub eventi, configurare, informazioni dettagliate
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985661"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="a1a4e-104">Configurare l'hub eventi</span><span class="sxs-lookup"><span data-stu-id="a1a4e-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a1a4e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a1a4e-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1a4e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1a4e-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a1a4e-107">Scopri come configurare l'hub eventi in modo che possa inserire eventi Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="a1a4e-108">Configurare il provider di risorse necessario nella sottoscrizione dell'hub eventi</span><span class="sxs-lookup"><span data-stu-id="a1a4e-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="a1a4e-109">Accedere al [portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a1a4e-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="a1a4e-110">Select **Subscriptions { Select the subscription the event hub will be deployed \> ***to***} \> Resource providers**.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="a1a4e-111">Verificare che **microsoft.Insights** Provider sia registrato.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="a1a4e-112">In caso contrario, registrarlo.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-112">Otherwise, register it.</span></span>

![Immagine dei provider di risorse in Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="a1a4e-114">Setup Azure Active Directory App Registration</span><span class="sxs-lookup"><span data-stu-id="a1a4e-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="a1a4e-115">! [NOTA] Devi avere il ruolo di amministratore o Azure Active Directory (AAD) per consentire agli utenti non amministratori di registrare le app.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="a1a4e-116">È inoltre necessario disporre di un ruolo Proprietario o Amministratore accesso utente per assegnare un ruolo all'entità servizio.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="a1a4e-117">Per ulteriori informazioni, vedere [Create an Azure AD app & service principal in the portal - Microsoft Identity Platform Microsoft \| Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="a1a4e-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="a1a4e-118">Crea una nuova registrazione (che crea intrinsecamente un'entità servizio) in Azure Active Directory **\> app Nuova \> registrazione.**</span><span class="sxs-lookup"><span data-stu-id="a1a4e-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="a1a4e-119">Compilare il modulo con il solo nome (non è necessario alcun URI di reindirizzamento).</span><span class="sxs-lookup"><span data-stu-id="a1a4e-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![Immagine della registrazione di un'applicazione](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Immagine delle informazioni di panoramica](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="a1a4e-122">Creare un segreto facendo clic su **Certificati & segreti Nuovo segreto \> client**:</span><span class="sxs-lookup"><span data-stu-id="a1a4e-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![Immagine di certificati e segreti](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="a1a4e-124">Non sarà possibile accedere di nuovo **al segreto client, quindi assicurarsi di salvarlo.**</span><span class="sxs-lookup"><span data-stu-id="a1a4e-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="a1a4e-125">Spazio dei nomi Dell'hub eventi di installazione</span><span class="sxs-lookup"><span data-stu-id="a1a4e-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="a1a4e-126">Creare uno spazio dei nomi hub eventi:</span><span class="sxs-lookup"><span data-stu-id="a1a4e-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="a1a4e-127">Vai **a Hub \> eventi** Aggiungi e seleziona il livello di prezzo, le unità di velocità effettiva e l'gonfiazione automatica (richiede prezzi standard e sotto funzionalità) appropriati per il carico previsto.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="a1a4e-128">Per altre informazioni, vedi [Prezzi - Hub eventi \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="a1a4e-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="a1a4e-129">Puoi usare un hub eventi esistente, ma la velocità effettiva e la scalabilità sono impostate a livello di spazio dei nomi, quindi è consigliabile posizionare un hub eventi nel relativo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![Immagine dello spazio dei nomi dell'hub eventi](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="a1a4e-131">Sarà inoltre necessario l'ID risorsa di questo spazio dei nomi dell'hub eventi.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="a1a4e-132">Passare alla pagina dello spazio dei nomi Hub eventi di Azure \> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="a1a4e-133">Copiare il testo in ID risorsa e registrarlo per l'utilizzo durante la sezione Configurazione M365 riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![Immagine delle proprietà](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="a1a4e-135">Dopo aver creato lo spazio dei nomi hub eventi, dovrai aggiungere l'entità servizio di registrazione app come lettore, ricevitore di dati hub eventi di Azure e l'utente che accederà a Microsoft 365 Defender come collaboratore (questa operazione può essere eseguita anche a livello di gruppo di risorse o di sottoscrizione).</span><span class="sxs-lookup"><span data-stu-id="a1a4e-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="a1a4e-136">Questa operazione viene eseguita in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify in **Role assignments**:</span><span class="sxs-lookup"><span data-stu-id="a1a4e-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![Immagine del controllo di accesso](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="a1a4e-138">Hub eventi di installazione</span><span class="sxs-lookup"><span data-stu-id="a1a4e-138">Setup Event Hub</span></span>


<span data-ttu-id="a1a4e-139">**Opzione 1:**</span><span class="sxs-lookup"><span data-stu-id="a1a4e-139">**Option 1:**</span></span>

<span data-ttu-id="a1a4e-140">Puoi creare un hub eventi  all'interno dello spazio dei nomi e tutti i tipi di evento (tabelle) selezionati per l'esportazione verranno scritti in questo **hub** eventi.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="a1a4e-141">**Opzione 2:**</span><span class="sxs-lookup"><span data-stu-id="a1a4e-141">**Option 2:**</span></span>

<span data-ttu-id="a1a4e-142">Invece di esportare tutti i tipi di evento (tabelle) in un unico hub eventi, puoi esportare ogni tabella in un hub eventi diverso all'interno dello spazio dei nomi dell'hub eventi (un hub eventi per ogni tipo di evento).</span><span class="sxs-lookup"><span data-stu-id="a1a4e-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="a1a4e-143">In questa opzione, Microsoft 365 Defender gli hub eventi verranno creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="a1a4e-144">Se si usa uno spazio  dei nomi Hub eventi che non fa parte di un cluster hub eventi, sarà possibile scegliere fino a 10 tipi di evento (tabelle) da esportare in ogni Impostazioni di esportazione definito, a causa di una limitazione di Azure di 10 hub eventi per spazio dei nomi hub eventi.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="a1a4e-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a1a4e-145">For example:</span></span>

![Immagine dell'hub eventi di esempio](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="a1a4e-147">Se si sceglie questa opzione, è possibile passare alla sezione Configura Microsoft 365 Defender [per inviare tabelle di posta](#configure-microsoft-365-defender-to-send-email-tables) elettronica.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="a1a4e-148">Crea un hub eventi all'interno dello spazio dei nomi selezionando **Hub eventi + Hub \> eventi.**</span><span class="sxs-lookup"><span data-stu-id="a1a4e-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="a1a4e-149">Il conteggio delle partizioni consente una velocità effettiva aggiuntiva tramite parallelismo, quindi è consigliabile aumentare questo numero in base al carico previsto.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="a1a4e-150">Sono consigliati i valori predefiniti Conservazione messaggi e Acquisizione di 1 e Disattivato.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![Immagine della creazione dell'hub eventi](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="a1a4e-152">Per questo hub eventi (non lo spazio dei nomi) dovrai configurare un criterio di accesso condiviso con Invia, Ascolta attestazioni.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="a1a4e-153">Fare clic sul proprio Hub eventi Criteri di accesso condiviso **\> \> +** Aggiungi e quindi assegnargli un nome di criterio (non usato altrove) e selezionare **Invia** e **ascolta**.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![Immagine dei criteri di accesso condiviso](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="a1a4e-155">Configurare Microsoft 365 Defender inviare tabelle di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a1a4e-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="a1a4e-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span><span class="sxs-lookup"><span data-stu-id="a1a4e-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="a1a4e-157">Accedere a Microsoft 365 Defender <https://security.microsoft.com> con un account che soddisfi tutti i requisiti di ruolo seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1a4e-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="a1a4e-158">Ruolo collaboratore a livello di risorsa spazio *dei nomi* Hub eventi o superiore per l'hub eventi in cui verrà esportato.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="a1a4e-159">Senza questo si riceverà un errore di esportazione quando si tenta di salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="a1a4e-160">Ruolo amministratore globale o amministratore della sicurezza nel tenant associato a Microsoft 365 Defender e Azure.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![Immagine del portale di sicurezza](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="a1a4e-162">Fare clic **su Esportazione dati non elaborati \> +Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="a1a4e-163">A questo punto verranno utilizzati i dati registrati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="a1a4e-164">**Nome**: è locale e deve essere qualsiasi cosa funzioni nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="a1a4e-165">**Inoltra eventi all'hub eventi**: seleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="a1a4e-166">**ID risorsa hub evento**: ID risorsa dello spazio dei nomi dell'hub eventi registrato in precedenza durante la configurazione dell'hub eventi.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="a1a4e-167">**Event-Hub name**: Se hai creato un hub eventi all'interno dello spazio dei nomi dell'hub eventi, incolla il nome dell'hub eventi registrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="a1a4e-168">Se scegli di consentire Microsoft 365 Defender hub eventi per tipi di evento (tabelle), lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="a1a4e-169">**Tipi di evento:** selezionare le tabelle ricerca avanzata che si desidera inoltrare all'hub eventi e quindi alla tua app personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="a1a4e-170">Le tabelle degli avvisi Microsoft 365 Defender, le tabelle dispositivi sono di Microsoft Defender for Endpoint (EDR) e le tabelle di posta elettronica sono di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a1a4e-171">Gli eventi di posta elettronica registrano tutte le transazioni di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="a1a4e-172">Vengono registrati anche l'URL (SafeLinks), l'allegato (allegati Safe) e gli eventi di post-recapito (ZAP) e possono essere aggiunti al campo Eventi di posta elettronica nel campo NetworkMessageId.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![Immagine delle impostazioni dell'API di streaming](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="a1a4e-174">Assicurati di fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="a1a4e-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="a1a4e-175">Verificare che gli eventi vengano esportati nell'hub eventi</span><span class="sxs-lookup"><span data-stu-id="a1a4e-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="a1a4e-176">Puoi verificare che gli eventi vengano inviati all'hub eventi eseguendo una query di ricerca avanzata di base.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="a1a4e-177">Selezionare **Ricerca avanzata query di \> \> ricerca** e immettere la query seguente:</span><span class="sxs-lookup"><span data-stu-id="a1a4e-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="a1a4e-178">Questo ti mostrerà quanti messaggi di posta elettronica sono stati ricevuti nell'ultima ora uniti in tutte le altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="a1a4e-179">Ti mostrerà anche se vengono visualizzati eventi che potrebbero essere esportati nell'hub eventi.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="a1a4e-180">Se questo conteggio mostra 0, non verrà visualizzato alcun dato nell'hub eventi.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![Immagine della ricerca avanzata](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="a1a4e-182">Dopo aver verificato che sono presenti dati da esportare, è possibile visualizzare l'hub eventi per verificare che i messaggi siano in arrivo.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="a1a4e-183">Questa operazione può richiedere fino a un'ora.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="a1a4e-184">In Azure, andare a Hub eventi Fare clic sugli hub eventi dello spazio dei nomi **\> Fare clic \> \> sull'hub eventi.**</span><span class="sxs-lookup"><span data-stu-id="a1a4e-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="a1a4e-185">In **Panoramica** scorrere verso il basso e nel grafico Messaggi dovrebbe essere visualizzato Messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="a1a4e-186">Se non vedi alcun risultato, non ci saranno messaggi per l'inserimento dell'app personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![Immagine della scheda Panoramica con i messaggi](../../media/e88060e315d76e74269a3fc866df047f.png)
