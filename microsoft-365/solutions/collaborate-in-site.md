---
title: Collaborare con gli utenti guest a un sito
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni su come collaborare con gli utenti in un sito di SharePoint.
ms.openlocfilehash: 3a7c14cc4cd31961b0d4c1054f88b5ed276b3b1a
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604755"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="7d61d-103">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="7d61d-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="7d61d-104">Se è necessario collaborare con gli utenti tra documenti, dati ed elenchi, è possibile utilizzare un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7d61d-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="7d61d-105">I siti di SharePoint moderni sono connessi a gruppi di Office 365 che possono gestire l'appartenenza al sito e fornire strumenti di collaborazione aggiuntivi quali una cassetta postale condivisa e un calendario.</span><span class="sxs-lookup"><span data-stu-id="7d61d-105">Modern SharePoint sites are connected to Office 365 Groups which can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="7d61d-106">In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare un sito di SharePoint per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7d61d-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="7d61d-107">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="7d61d-107">Video demonstration</span></span>

<span data-ttu-id="7d61d-108">In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="7d61d-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="7d61d-109">Impostazioni delle relazioni organizzative di Azure</span><span class="sxs-lookup"><span data-stu-id="7d61d-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="7d61d-110">La condivisione in Microsoft 365 è regolata al livello più alto dalle impostazioni delle relazioni organizzative in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7d61d-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="7d61d-111">Se la condivisione Guest è disabilitata o limitata in Azure AD, queste verranno sostituite da tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d61d-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="7d61d-112">Controllare le impostazioni delle relazioni organizzative per garantire che la condivisione con gli ospiti non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="7d61d-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="7d61d-114">Per impostare le impostazioni delle relazioni organizzative</span><span class="sxs-lookup"><span data-stu-id="7d61d-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="7d61d-115">Accedere a Microsoft Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="7d61d-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="7d61d-116">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="7d61d-117">Nel riquadro **Panoramica** fare clic su **relazioni organizzative**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="7d61d-118">Nel riquadro **relazioni organizzative** fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="7d61d-119">Verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="7d61d-120">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="7d61d-121">Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** .</span><span class="sxs-lookup"><span data-stu-id="7d61d-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="7d61d-122">Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="7d61d-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="office-365-groups-guest-settings"></a><span data-ttu-id="7d61d-123">Office 365 gruppi Guest Settings</span><span class="sxs-lookup"><span data-stu-id="7d61d-123">Office 365 Groups guest settings</span></span>

<span data-ttu-id="7d61d-124">I siti di SharePoint moderni utilizzano i gruppi di Office 365 per controllare l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="7d61d-124">Modern SharePoint sites use Office 365 Groups to control site access.</span></span> <span data-ttu-id="7d61d-125">Le impostazioni di Office 365 groups Guest devono essere attivate affinché l'accesso guest in siti di SharePoint funzioni.</span><span class="sxs-lookup"><span data-stu-id="7d61d-125">The Office 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Screenshot delle impostazioni guest di Gruppi di Office 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="7d61d-127">Per impostare le impostazioni di Office 365 groups Guest</span><span class="sxs-lookup"><span data-stu-id="7d61d-127">To set Office 365 Groups guest settings</span></span>

1. <span data-ttu-id="7d61d-128">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, espandere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-128">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="7d61d-129">Fare clic su **servizi & componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="7d61d-129">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="7d61d-130">Nell'elenco, fare clic su **gruppi di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-130">In the list, click **Office 365 Groups**.</span></span>
4. <span data-ttu-id="7d61d-131">Verificare che i membri del gruppo Consenti al di **fuori dell'organizzazione accedano al contenuto del gruppo** e che i proprietari del **gruppo aggiungano persone all'esterno dell'organizzazione ai gruppi di caselle di** controllo siano entrambe controllate.</span><span class="sxs-lookup"><span data-stu-id="7d61d-131">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="7d61d-132">Se sono state apportate modifiche, fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-132">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="7d61d-133">Impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d61d-133">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="7d61d-134">Affinché gli utenti dispongano dell'accesso ai siti di SharePoint, le impostazioni di condivisione a livello dell'organizzazione di SharePoint devono consentire la condivisione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7d61d-134">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="7d61d-135">Le impostazioni a livello di organizzazione determinano le impostazioni disponibili per i singoli siti.</span><span class="sxs-lookup"><span data-stu-id="7d61d-135">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="7d61d-136">Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7d61d-136">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="7d61d-137">Se si desidera consentire la condivisione di file e cartelle non autenticata, scegliere **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-137">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="7d61d-138">Se si desidera garantire che tutti gli utenti esterni all'organizzazione debbano eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-138">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="7d61d-139">Scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7d61d-139">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="7d61d-141">Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d61d-141">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="7d61d-142">Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento a sinistra, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-142">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="7d61d-143">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-143">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="7d61d-144">Assicurarsi che la condivisione esterna per SharePoint sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-144">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="7d61d-145">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-145">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="7d61d-146">Creare un sito</span><span class="sxs-lookup"><span data-stu-id="7d61d-146">Create a site</span></span>

<span data-ttu-id="7d61d-147">Il passaggio successivo consiste nel creare il sito che si intende utilizzare per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7d61d-147">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="7d61d-148">Per creare un sito</span><span class="sxs-lookup"><span data-stu-id="7d61d-148">To create a site</span></span>
1. <span data-ttu-id="7d61d-149">Nell'interfaccia di amministrazione di SharePoint, in **Siti** fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-149">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="7d61d-150">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-150">Click **Create**.</span></span>
3. <span data-ttu-id="7d61d-151">Fare clic su **sito del team**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-151">Click **Team site**.</span></span>
4. <span data-ttu-id="7d61d-152">Digitare il nome di un sito e immettere un nome per il proprietario del gruppo (proprietario del sito).</span><span class="sxs-lookup"><span data-stu-id="7d61d-152">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="7d61d-153">In **Impostazioni avanzate**scegliere se si desidera che sia un sito pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="7d61d-153">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="7d61d-154">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-154">Click **Next**.</span></span>
7. <span data-ttu-id="7d61d-155">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-155">Click **Finish**.</span></span>

<span data-ttu-id="7d61d-156">Gli utenti verranno invitati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7d61d-156">We'll invite users later.</span></span> <span data-ttu-id="7d61d-157">Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito.</span><span class="sxs-lookup"><span data-stu-id="7d61d-157">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="7d61d-158">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d61d-158">SharePoint site level sharing settings</span></span>

<span data-ttu-id="7d61d-159">Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il sito.</span><span class="sxs-lookup"><span data-stu-id="7d61d-159">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="7d61d-160">Ad esempio, se si impostano le impostazioni a livello di organizzazione per tutti gli **utenti**, ma si desidera che tutti gli ospiti eseguano l'autenticazione per questo sito, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su **ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-160">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="7d61d-161">Si noti che il sito non può essere condiviso con persone non autenticate (impostazione di**tutti** gli utenti), ma è possibile eseguire singoli file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="7d61d-161">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="7d61d-163">Per impostare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="7d61d-163">To set site-level sharing settings</span></span>
1. <span data-ttu-id="7d61d-164">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-164">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="7d61d-165">Selezionare il sito appena creato.</span><span class="sxs-lookup"><span data-stu-id="7d61d-165">Select the site that you just created.</span></span>
3. <span data-ttu-id="7d61d-166">Sulla barra multifunzione fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-166">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="7d61d-167">Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-167">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="7d61d-168">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-168">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="7d61d-169">Invitare gli utenti</span><span class="sxs-lookup"><span data-stu-id="7d61d-169">Invite users</span></span>

<span data-ttu-id="7d61d-170">Le impostazioni di condivisione Guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e ospiti al sito.</span><span class="sxs-lookup"><span data-stu-id="7d61d-170">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="7d61d-171">L'accesso al sito è controllato tramite il gruppo Office 365 associato, quindi verranno aggiunti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7d61d-171">Site access is controlled through the associated Office 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="7d61d-172">Per invitare gli utenti interni a un gruppo</span><span class="sxs-lookup"><span data-stu-id="7d61d-172">To invite internal users to a group</span></span>
1. <span data-ttu-id="7d61d-173">Passare al sito in cui si desidera aggiungere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7d61d-173">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="7d61d-174">Fare clic su **membri** in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="7d61d-174">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="7d61d-175">Fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-175">Click **Add members**.</span></span>
4. <span data-ttu-id="7d61d-176">Digitare i nomi o gli indirizzi di posta elettronica degli utenti che si desidera invitare al sito e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-176">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="7d61d-177">Gli utenti guest non possono essere aggiunti dal sito.</span><span class="sxs-lookup"><span data-stu-id="7d61d-177">Guest users can't be added from the site.</span></span> <span data-ttu-id="7d61d-178">È necessario aggiungerli utilizzando Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="7d61d-178">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="7d61d-179">Per invitare gli ospiti a un gruppo</span><span class="sxs-lookup"><span data-stu-id="7d61d-179">To invite guests to a group</span></span>
1. <span data-ttu-id="7d61d-180">In **gruppi**, in Outlook sul Web, fare clic sul gruppo in cui si desidera aggiungere i membri.</span><span class="sxs-lookup"><span data-stu-id="7d61d-180">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="7d61d-181">Aprire la scheda contatto di gruppo e quindi, in **altre opzioni** (...), fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-181">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="7d61d-182">Digitare gli indirizzi di posta elettronica degli utenti che si desidera invitare e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-182">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="7d61d-183">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7d61d-183">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d61d-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d61d-184">See Also</span></span>

[<span data-ttu-id="7d61d-185">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="7d61d-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="7d61d-186">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="7d61d-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="7d61d-187">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="7d61d-187">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="7d61d-188">[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="7d61d-188">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

