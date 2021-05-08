---
title: Avviare il portale usando l'utilità di pianificazione di avvio del portale
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In questo articolo viene descritto come avviare il portale tramite l'utilità di pianificazione di avvio del portale
ms.openlocfilehash: 1e62446054f91ff5d2c99520ca65c1681d899ac9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272073"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="ef62f-103">Avviare il portale utilizzando l'utilità di pianificazione di avvio di SharePoint Portal</span><span class="sxs-lookup"><span data-stu-id="ef62f-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="ef62f-104">Un portale è un sito di comunicazione di SharePoint nella rete Intranet con traffico elevato, un sito che ha da 10.000 a oltre 100.000 visualizzatori nel corso di diverse settimane.</span><span class="sxs-lookup"><span data-stu-id="ef62f-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="ef62f-105">Utilizzare l'utilità di pianificazione di avvio del portale per avviare il portale per garantire agli utenti un'esperienza di visualizzazione ottimale quando accedono al nuovo portale di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef62f-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="ef62f-106">L'utilità di pianificazione per l'avvio del portale è progettata per consentire di seguire un approccio di implementazione in più fasi, tramite l'invio in batch dei visualizzatori e la gestione dei reindirizzamenti DEGLI URL per il nuovo portale.</span><span class="sxs-lookup"><span data-stu-id="ef62f-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="ef62f-107">Durante l'avvio di ogni ondata, è possibile raccogliere il feedback degli utenti, monitorare le prestazioni del portale e sospendere l'avvio per risolvere i problemi prima di procedere con l'onda successiva.</span><span class="sxs-lookup"><span data-stu-id="ef62f-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="ef62f-108">Ulteriori informazioni su come pianificare [l'avvio di un portale in SharePoint.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="ef62f-108">Learn more about how to [plan a portal launch in SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> 

<span data-ttu-id="ef62f-109">**Esistono due tipi di reindirizzamenti:**</span><span class="sxs-lookup"><span data-stu-id="ef62f-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="ef62f-110">**Bidirezionale:** avviare un nuovo portale di SharePoint moderno per sostituire un portale classico o moderno di SharePoint esistente</span><span class="sxs-lookup"><span data-stu-id="ef62f-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="ef62f-111">**Reindirizzare a una pagina temporanea:** avviare un nuovo portale di SharePoint moderno senza portale di SharePoint esistente</span><span class="sxs-lookup"><span data-stu-id="ef62f-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="ef62f-112">Le autorizzazioni del sito devono essere impostate separatamente dalle ondate durante l'avvio.</span><span class="sxs-lookup"><span data-stu-id="ef62f-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="ef62f-113">Ad esempio, se si rilascia un portale a livello di organizzazione, è possibile impostare le autorizzazioni su "Tutti tranne gli utenti esterni", quindi separare gli utenti in gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef62f-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="ef62f-114">L'aggiunta di un gruppo di sicurezza a un'onda non consente a tale gruppo di sicurezza di accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="ef62f-114">Adding a security group to a wave does not give that security group access to the site.</span></span> 


> [!NOTE]
> - <span data-ttu-id="ef62f-115">Questa funzionalità sarà accessibile  dal pannello Impostazioni nella home page dei siti di comunicazione di SharePoint per i clienti con rilascio mirato a partire da maggio 2021 e sarà disponibile per tutti i clienti entro luglio 2021</span><span class="sxs-lookup"><span data-stu-id="ef62f-115">This will feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="ef62f-116">La versione powershell di questo strumento è disponibile oggi</span><span class="sxs-lookup"><span data-stu-id="ef62f-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="ef62f-117">Questa funzionalità può essere utilizzata solo nei siti di comunicazione di SharePoint moderni</span><span class="sxs-lookup"><span data-stu-id="ef62f-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="ef62f-118">È necessario disporre delle autorizzazioni di proprietario del sito per personalizzare e pianificare l'avvio di un portale</span><span class="sxs-lookup"><span data-stu-id="ef62f-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="ef62f-119">Gli avvii devono essere pianificati con almeno sette giorni di anticipo e ogni onda può durare da uno a sette giorni</span><span class="sxs-lookup"><span data-stu-id="ef62f-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="ef62f-120">Il numero di onde richieste viene determinato automaticamente dal numero previsto di utenti</span><span class="sxs-lookup"><span data-stu-id="ef62f-120">The number of waves required is automatically determined by the expected number of users</span></span> 
> - <span data-ttu-id="ef62f-121">Prima di pianificare l'avvio di un portale, è necessario eseguire lo strumento Diagnostica pagine per [SharePoint](https://aka.ms/perftool) per verificare che la home page del sito sia integra</span><span class="sxs-lookup"><span data-stu-id="ef62f-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="ef62f-122">Al termine dell'avvio, tutti gli utenti con autorizzazioni per il sito potranno accedere al nuovo sito</span><span class="sxs-lookup"><span data-stu-id="ef62f-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="ef62f-123">Se l'organizzazione usa [Viva Connections,](https://docs.microsoft.com/SharePoint/viva-connections)gli utenti potrebbero visualizzare l'icona dell'organizzazione nella barra dell'app Di Microsoft Teams, tuttavia, quando l'icona è selezionata, gli utenti non potranno accedere al portale fino all'avvio dell'ondata</span><span class="sxs-lookup"><span data-stu-id="ef62f-123">If your organization is using [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="ef62f-124">Questa funzionalità non è disponibile per i piani di Office 365 Germany, Office 365 gestito da 21Vianet (Cina) o Microsoft 365 US Government</span><span class="sxs-lookup"><span data-stu-id="ef62f-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="ef62f-125">Comprendere le differenze tra le opzioni dell'utilità di pianificazione di avvio del portale:</span><span class="sxs-lookup"><span data-stu-id="ef62f-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="ef62f-126">In precedenza, gli avvii del portale potevano essere pianificati solo tramite PowerShell di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef62f-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="ef62f-127">A questo punto, sono disponibili due opzioni che consentono di pianificare e gestire l'avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="ef62f-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="ef62f-128">Informazioni sulle differenze principali tra entrambi gli strumenti:</span><span class="sxs-lookup"><span data-stu-id="ef62f-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="ef62f-129">**Versione powershell di SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="ef62f-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="ef62f-130">Le credenziali di amministratore sono necessarie per usare [PowerShell di SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="ef62f-130">Admin credentials are required to use [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span></span> 
- <span data-ttu-id="ef62f-131">Requisito minimo di un'onda</span><span class="sxs-lookup"><span data-stu-id="ef62f-131">Minimum requirement of one wave</span></span> 
- <span data-ttu-id="ef62f-132">Pianificare l'avvio in base al fuso orario UTC (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="ef62f-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="ef62f-133">**Versione nel prodotto:**</span><span class="sxs-lookup"><span data-stu-id="ef62f-133">**In-product version:**</span></span>

- <span data-ttu-id="ef62f-134">Le credenziali del proprietario del sito sono necessarie</span><span class="sxs-lookup"><span data-stu-id="ef62f-134">Site owner credentials are required</span></span> 
- <span data-ttu-id="ef62f-135">Requisito minimo di due onde</span><span class="sxs-lookup"><span data-stu-id="ef62f-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="ef62f-136">Pianificare l'avvio in base al fuso orario locale del portale, come indicato nelle impostazioni internazionali</span><span class="sxs-lookup"><span data-stu-id="ef62f-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>



## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="ef62f-137">Introduzione all'utilità di pianificazione per l'avvio del portale</span><span class="sxs-lookup"><span data-stu-id="ef62f-137">Get started using the Portal launch scheduler</span></span>

1.  <span data-ttu-id="ef62f-138">Prima di utilizzare lo strumento Utilità di pianificazione di avvio  [portale,](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) aggiungere tutti gli utenti che dovranno accedere al sito tramite le autorizzazioni sito come proprietario del sito, membro del sito o visitatore.</span><span class="sxs-lookup"><span data-stu-id="ef62f-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2.  <span data-ttu-id="ef62f-139">Quindi, iniziare a pianificare l'avvio del portale accedendo all'utilità di pianificazione di avvio del portale in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef62f-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

    <span data-ttu-id="ef62f-140">**Opzione 1:** le prime volte che si modificano e ripubblicano le modifiche alla home page o fino alla home page versione 3.0, verrà richiesto di utilizzare lo strumento Utilità di pianificazione di avvio portale.</span><span class="sxs-lookup"><span data-stu-id="ef62f-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="ef62f-141">Selezionare **Pianifica avvio** per procedere con la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ef62f-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="ef62f-142">Oppure seleziona **Ripubblica** per ripubblicare le modifiche alla pagina senza pianificare l'avvio.</span><span class="sxs-lookup"><span data-stu-id="ef62f-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>
    
    ![Immagine del prompt per l'utilizzo dell'utilità di pianificazione di avvio del portale durante la ripubblicazione della home page](../media/portal-launch-republish-2.png)
    
    <span data-ttu-id="ef62f-144">**Opzione 2:** in qualsiasi momento, è possibile passare alla home page del sito di comunicazione di SharePoint, selezionare **Impostazioni** e **quindi** Pianificare l'avvio del sito per pianificare l'avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="ef62f-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>
    
    ![Immagine del riquadro Impostazioni con l'opzione Pianifica avvio sito evidenziata](../media/portal-launch-settings-2.png)

3.  <span data-ttu-id="ef62f-146">Successivamente, confermare il punteggio di integrità del portale e apportare miglioramenti al portale, se necessario, utilizzando lo strumento Diagnostica pagine per [SharePoint](https://aka.ms/perftool) fino a quando il portale non riceve un **punteggio Integro.**</span><span class="sxs-lookup"><span data-stu-id="ef62f-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="ef62f-147">Selezionare quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ef62f-147">Then, select **Next**.</span></span>

    ![Immagine dello strumento utilità di pianificazione di avvio del portale](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > <span data-ttu-id="ef62f-149">Il nome e la descrizione del sito non possono essere modificati dall'utilità  di pianificazione di avvio del portale e possono essere modificati selezionando **Impostazioni** e quindi Informazioni sito dalla home page.</span><span class="sxs-lookup"><span data-stu-id="ef62f-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>
 
4.  <span data-ttu-id="ef62f-150">Selezionare **il numero di utenti previsti** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ef62f-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="ef62f-151">Questa figura rappresenta il numero di utenti che probabilmente dovranno accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="ef62f-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="ef62f-152">L'utilità di pianificazione di avvio del portale determinerà automaticamente il numero ideale di onde a seconda degli utenti previsti come questo:</span><span class="sxs-lookup"><span data-stu-id="ef62f-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>
    
    - <span data-ttu-id="ef62f-153">Meno di 10.000 utenti: due onde</span><span class="sxs-lookup"><span data-stu-id="ef62f-153">Less than 10k users: Two waves</span></span>
    - <span data-ttu-id="ef62f-154">Da 10.000 a 30.000 utenti: tre onde</span><span class="sxs-lookup"><span data-stu-id="ef62f-154">10k to 30k users: Three waves</span></span> 
    - <span data-ttu-id="ef62f-155">Da 30.000 a 100.000 utenti: cinque onde</span><span class="sxs-lookup"><span data-stu-id="ef62f-155">30k+ to 100k users: Five waves</span></span>
    - <span data-ttu-id="ef62f-156">Più di 100.000 utenti: cinque onde e contatta il team dell'account Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef62f-156">More than 100k users: Five waves and contact your Microsoft account team</span></span>

5.  <span data-ttu-id="ef62f-157">Quindi, determinare **il tipo di reindirizzamento** necessario:</span><span class="sxs-lookup"><span data-stu-id="ef62f-157">Then, determine the **Type of redirect** needed:</span></span>

    <span data-ttu-id="ef62f-158">Opzione 1: Inviare utenti a una pagina di **SharePoint esistente (bidirezionale):** utilizzare questa opzione quando si avvia un nuovo portale di SharePoint moderno per sostituire un portale di SharePoint esistente.</span><span class="sxs-lookup"><span data-stu-id="ef62f-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="ef62f-159">Gli utenti in ondate attive verranno reindirizzati al nuovo sito indipendentemente dal fatto che si snavigare verso il sito vecchio o nuovo.</span><span class="sxs-lookup"><span data-stu-id="ef62f-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="ef62f-160">Gli utenti in un'ondata non avviata che tentano di accedere al nuovo sito verranno reindirizzati al sito precedente fino all'avvio dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="ef62f-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>
    
    > [!NOTE] 
    > <span data-ttu-id="ef62f-161">Quando si utilizza l'opzione bidirezionale, la persona che pianifica l'avvio deve disporre anche delle autorizzazioni di proprietario del sito per l'altro portale di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef62f-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>
       
    <span data-ttu-id="ef62f-162">**Opzione 2:** Inviare gli utenti a una pagina temporanea rigenerata automaticamente (reindirizzamento temporaneo delle pagine): utilizzare un reindirizzamento temporaneo della pagina quando non esiste un portale di SharePoint esistente.</span><span class="sxs-lookup"><span data-stu-id="ef62f-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="ef62f-163">Gli utenti vengono indirizzati a un nuovo portale di SharePoint moderno e se un utente è in un'ondata che non è stata avviata, verrà reindirizzato a una pagina temporanea.</span><span class="sxs-lookup"><span data-stu-id="ef62f-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>
    
    <span data-ttu-id="ef62f-164">**Opzione 3: Inviare gli** utenti a una pagina esterna: fornire un URL esterno a un'esperienza di pagina di destinazione temporanea fino all'avvio dell'ondata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ef62f-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>
    
6.  <span data-ttu-id="ef62f-165">Suddividere il pubblico in onde.</span><span class="sxs-lookup"><span data-stu-id="ef62f-165">Break up your audience into waves.</span></span> <span data-ttu-id="ef62f-166">Aggiungere fino a 20 gruppi di sicurezza per ogni ondata.</span><span class="sxs-lookup"><span data-stu-id="ef62f-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="ef62f-167">I dettagli dell'onda possono essere modificati fino al lancio di ogni onda.</span><span class="sxs-lookup"><span data-stu-id="ef62f-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="ef62f-168">Ogni onda può durare almeno un giorno (24 ore) e al massimo sette giorni.</span><span class="sxs-lookup"><span data-stu-id="ef62f-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="ef62f-169">Ciò consente a SharePoint e all'ambiente tecnico di accumulare e ridimensionare il volume di utenti del sito.</span><span class="sxs-lookup"><span data-stu-id="ef62f-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="ef62f-170">Quando si pianifica un avvio tramite l'interfaccia utente, il fuso orario si basa sulle impostazioni internazionali del sito.</span><span class="sxs-lookup"><span data-stu-id="ef62f-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span> 

    >[!NOTE] 
    > - <span data-ttu-id="ef62f-171">L'utilità di pianificazione per l'avvio del portale avrà automaticamente un minimo di 2 onde.</span><span class="sxs-lookup"><span data-stu-id="ef62f-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="ef62f-172">Tuttavia, la versione powershell di questo strumento consentirà 1 onda.</span><span class="sxs-lookup"><span data-stu-id="ef62f-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
    >  - <span data-ttu-id="ef62f-173">I gruppi di Microsoft 365 non sono supportati da questa versione dell'utilità di pianificazione di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="ef62f-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="ef62f-174">Determinare chi deve visualizzare immediatamente il sito e immettere le informazioni nel **campo Utenti esenti da ondate.**</span><span class="sxs-lookup"><span data-stu-id="ef62f-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="ef62f-175">Questi utenti sono esclusi dalle ondate e non verranno reindirizzati prima, durante o dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="ef62f-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

8.  <span data-ttu-id="ef62f-176">Confermare i dettagli di avvio del portale e selezionare **Pianifica**.</span><span class="sxs-lookup"><span data-stu-id="ef62f-176">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="ef62f-177">Dopo la pianificazione dell'avvio, tutte le modifiche alla home page del portale di SharePoint dovranno ricevere un risultato di diagnostica integro prima che l'avvio del portale venga ripreso.</span><span class="sxs-lookup"><span data-stu-id="ef62f-177">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>


## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="ef62f-178">Apportare modifiche a un avvio pianificato del portale</span><span class="sxs-lookup"><span data-stu-id="ef62f-178">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="ef62f-179">I dettagli di avvio possono essere modificati per ogni ondata fino alla data di avvio dell'onda.</span><span class="sxs-lookup"><span data-stu-id="ef62f-179">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span> 

1.  <span data-ttu-id="ef62f-180">Per modificare i dettagli di avvio del portale, passare a **Impostazioni** e selezionare **Pianifica avvio sito.**</span><span class="sxs-lookup"><span data-stu-id="ef62f-180">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2.  <span data-ttu-id="ef62f-181">Selezionare quindi **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ef62f-181">Then, select **Edit**.</span></span>
3.  <span data-ttu-id="ef62f-182">Dopo aver apportato le modifiche, selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="ef62f-182">When you are finished making your edits, select **Update**.</span></span>


## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="ef62f-183">Eliminare un avvio pianificato del portale</span><span class="sxs-lookup"><span data-stu-id="ef62f-183">Delete a scheduled portal launch</span></span>

<span data-ttu-id="ef62f-184">Gli avvii pianificati tramite lo strumento Utilità di pianificazione di avvio portale possono essere annullati o eliminati in qualsiasi momento anche se alcune onde sono già state avviate.</span><span class="sxs-lookup"><span data-stu-id="ef62f-184">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1.  <span data-ttu-id="ef62f-185">Per annullare l'avvio del portale, passare a **Impostazioni** e **Pianificare l'avvio del sito.**</span><span class="sxs-lookup"><span data-stu-id="ef62f-185">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2.  <span data-ttu-id="ef62f-186">Selezionare quindi **Elimina** e quindi, quando viene visualizzato il messaggio seguente, selezionare **di nuovo Elimina.**</span><span class="sxs-lookup"><span data-stu-id="ef62f-186">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

    ![Immagine dello strumento utilità di pianificazione di avvio del portale](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="ef62f-188">Usare l'utilità di pianificazione di avvio del portale di PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef62f-188">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="ef62f-189">Lo strumento utilità di pianificazione di avvio di SharePoint Portal era originariamente disponibile solo tramite PowerShell di [SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) e continuerà a essere supportato tramite PowerShell per i clienti che preferiscono questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ef62f-189">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="ef62f-190">Le stesse note all'inizio di questo articolo si applicano a entrambe le versioni dell'utilità di pianificazione di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="ef62f-190">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span> 

>[!NOTE]
> <span data-ttu-id="ef62f-191">Per utilizzare PowerShell di SharePoint, sono necessarie le autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="ef62f-191">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="ef62f-192">Verranno visualizzati i dettagli di avvio del portale per gli avvii creati in PowerShell e possono essere gestiti nel nuovo strumento Utilità di pianificazione di avvio portale in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef62f-192">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>


### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="ef62f-193">Configurazione dell'app e connessione a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ef62f-193">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="ef62f-194">[Scaricare l'ultima versione di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="ef62f-194">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef62f-p116">Se hai installato una versione precedente di SharePoint Online Management Shell, vai su Installazione applicazioni e disinstallare SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ef62f-p116">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="ef62f-196">Nella pagina Download Center selezionare la lingua e fare clic sul pulsante Scarica.</span><span class="sxs-lookup"><span data-stu-id="ef62f-196">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="ef62f-197">Ti verrà chiesto di scegliere tra il download di un file x64 e x86 con estensione msi.</span><span class="sxs-lookup"><span data-stu-id="ef62f-197">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="ef62f-198">Scaricare il file x64 se stai eseguendo la versione a 64 bit di Windows e il file x86 se stai eseguendo quella a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="ef62f-198">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="ef62f-199">Se non conosci quale versione stai eseguendo, vedere[Quale versione del sistema operativo Windows sto eseguendo?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="ef62f-199">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="ef62f-200">Dopo aver scaricato il file, eseguirlo e seguire i passaggi della configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="ef62f-200">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="ef62f-201">Connettiti a SharePoint come [amministratore globale o amministratore di SharePoint](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef62f-201">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="ef62f-202">Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="ef62f-202">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="ef62f-203">Visualizzare eventuali configurazioni di avvio del portale esistenti</span><span class="sxs-lookup"><span data-stu-id="ef62f-203">View any existing portal launch setups</span></span>

<span data-ttu-id="ef62f-204">Per verificare se sono presenti configurazioni di avvio del portale esistenti:</span><span class="sxs-lookup"><span data-stu-id="ef62f-204">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="ef62f-205">Pianificare un avvio del portale nel sito</span><span class="sxs-lookup"><span data-stu-id="ef62f-205">Schedule a portal launch on the site</span></span>

<span data-ttu-id="ef62f-206">Il numero di onde necessarie dipende dalle dimensioni di avvio previste.</span><span class="sxs-lookup"><span data-stu-id="ef62f-206">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="ef62f-207">Meno di 10.000 utenti: un'onda</span><span class="sxs-lookup"><span data-stu-id="ef62f-207">Less than 10k users: One wave</span></span>
- <span data-ttu-id="ef62f-208">Da 10.000 a 30.000 utenti: tre onde</span><span class="sxs-lookup"><span data-stu-id="ef62f-208">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="ef62f-209">Da 30.000 a 100.000 utenti: cinque onde</span><span class="sxs-lookup"><span data-stu-id="ef62f-209">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="ef62f-210">Più di 100.000 utenti: cinque onde e contatta il team dell'account Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef62f-210">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="ef62f-211">Passaggi per il reindirizzamento bidirezionale</span><span class="sxs-lookup"><span data-stu-id="ef62f-211">Steps for bidirectional redirection</span></span>

<span data-ttu-id="ef62f-212">Il reindirizzamento bidirezionale prevede l'avvio di un nuovo portale di SharePoint Online moderno per sostituire un portale classico o moderno di SharePoint esistente.</span><span class="sxs-lookup"><span data-stu-id="ef62f-212">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="ef62f-213">Gli utenti in ondate attive verranno reindirizzati al nuovo sito indipendentemente dal fatto che si snavigare verso il sito vecchio o nuovo.</span><span class="sxs-lookup"><span data-stu-id="ef62f-213">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="ef62f-214">Gli utenti in un'ondata non avviata che tentano di accedere al nuovo sito verranno reindirizzati al sito precedente fino all'avvio dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="ef62f-214">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="ef62f-215">Supportiamo solo il reindirizzamento tra la home page predefinita nel vecchio sito e la home page predefinita nel nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="ef62f-215">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="ef62f-216">Se si dispone di amministratori o proprietari che devono accedere ai siti vecchi e nuovi senza essere reindirizzati, assicurarsi che siano elencati utilizzando il `WaveOverrideUsers` parametro .</span><span class="sxs-lookup"><span data-stu-id="ef62f-216">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="ef62f-217">Per eseguire la migrazione a fasi degli utenti da un sito di SharePoint esistente a un nuovo sito di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="ef62f-217">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="ef62f-218">Eseguire il comando seguente per designare le ondate di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="ef62f-218">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="ef62f-219">Esempio:</span><span class="sxs-lookup"><span data-stu-id="ef62f-219">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="ef62f-220">Completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="ef62f-220">Complete validation.</span></span> <span data-ttu-id="ef62f-221">Il reindirizzamento può richiedere da 5 a 10 minuti per completare la configurazione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ef62f-221">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="ef62f-222">Passaggi per il reindirizzamento alla pagina temporanea</span><span class="sxs-lookup"><span data-stu-id="ef62f-222">Steps for redirection to temporary page</span></span>

<span data-ttu-id="ef62f-223">Il reindirizzamento temporaneo delle pagine deve essere utilizzato quando non esiste un portale di SharePoint esistente.</span><span class="sxs-lookup"><span data-stu-id="ef62f-223">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="ef62f-224">Gli utenti vengono indirizzati a un nuovo portale di SharePoint Online moderno in modo a fasi.</span><span class="sxs-lookup"><span data-stu-id="ef62f-224">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="ef62f-225">Se un utente è in un'ondata che non è stata avviata, verrà reindirizzato a una pagina temporanea (qualsiasi URL).</span><span class="sxs-lookup"><span data-stu-id="ef62f-225">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="ef62f-226">Eseguire il comando seguente per designare le ondate di avvio del portale.</span><span class="sxs-lookup"><span data-stu-id="ef62f-226">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="ef62f-227">Esempio:</span><span class="sxs-lookup"><span data-stu-id="ef62f-227">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="ef62f-228">Completare la convalida.</span><span class="sxs-lookup"><span data-stu-id="ef62f-228">Complete validation.</span></span> <span data-ttu-id="ef62f-229">Il reindirizzamento può richiedere da 5 a 10 minuti per completare la configurazione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ef62f-229">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="ef62f-230">Sospendere o riavviare l'avvio di un portale nel sito</span><span class="sxs-lookup"><span data-stu-id="ef62f-230">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="ef62f-231">Per sospendere l'avvio di un portale in corso e impedire temporaneamente che si verifichino imminenti progressioni delle onde, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ef62f-231">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="ef62f-232">Verificare che tutti gli utenti siano reindirizzati al sito precedente.</span><span class="sxs-lookup"><span data-stu-id="ef62f-232">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="ef62f-233">Per riavviare un avvio del portale sospeso, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ef62f-233">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="ef62f-234">Verificare che il reindirizzamento sia stato ripristinato.</span><span class="sxs-lookup"><span data-stu-id="ef62f-234">Validate that the redirection is now restored.</span></span> 

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="ef62f-235">Eliminare un avvio del portale nel sito</span><span class="sxs-lookup"><span data-stu-id="ef62f-235">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="ef62f-236">Eseguire il comando seguente per eliminare un avvio del portale pianificato o in corso per un sito.</span><span class="sxs-lookup"><span data-stu-id="ef62f-236">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="ef62f-237">Verificare che non si verifica alcun reindirizzamento per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ef62f-237">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="ef62f-238">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="ef62f-238">Learn more</span></span>

[<span data-ttu-id="ef62f-239">Pianificazione del piano di implementazione dell'avvio del portale in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ef62f-239">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="ef62f-240">Pianificare il sito di comunicazione</span><span class="sxs-lookup"><span data-stu-id="ef62f-240">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)