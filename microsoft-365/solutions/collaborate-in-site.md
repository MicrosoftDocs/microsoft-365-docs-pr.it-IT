---
title: Collaborare con gli utenti guest a un sito
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni sui passaggi di configurazione di Microsoft 365 necessari per configurare un sito di SharePoint per la collaborazione con gli utenti.
ms.openlocfilehash: cb3cfc52191be4bacfb9d84672131149082ee80e
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277563"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="37b8e-103">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="37b8e-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="37b8e-104">Se è necessario collaborare con gli utenti tra documenti, dati ed elenchi, è possibile utilizzare un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="37b8e-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="37b8e-105">I siti di SharePoint moderni sono connessi ai gruppi di Microsoft 365 e possono gestire l'appartenenza al sito e fornire strumenti di collaborazione aggiuntivi quali una cassetta postale condivisa e un calendario.</span><span class="sxs-lookup"><span data-stu-id="37b8e-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="37b8e-106">In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare un sito di SharePoint per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="37b8e-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="37b8e-107">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="37b8e-107">Video demonstration</span></span>

<span data-ttu-id="37b8e-108">In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="37b8e-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="37b8e-109">Impostazioni di collaborazione esterna di Azure</span><span class="sxs-lookup"><span data-stu-id="37b8e-109">Azure external collaboration settings</span></span>

<span data-ttu-id="37b8e-110">La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni delle relazioni organizzative in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="37b8e-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="37b8e-111">Se la condivisione Guest è disabilitata o limitata in Azure AD, queste verranno sostituite da tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37b8e-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="37b8e-112">Controllare le impostazioni di collaborazione esterna per assicurarsi che la condivisione con gli ospiti non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="37b8e-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Schermata della pagina impostazioni di collaborazione esterna di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="37b8e-114">Per impostare le impostazioni di collaborazione esterna:</span><span class="sxs-lookup"><span data-stu-id="37b8e-114">To set external collaboration settings:</span></span>


1. <span data-ttu-id="37b8e-115">Accedere a Microsoft Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="37b8e-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="37b8e-116">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="37b8e-117">Selezionare **identità esterne** e fare clic su **impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-117">Select **External Identities** and click on **External collaboration settings**.</span></span>
4. <span data-ttu-id="37b8e-118">Nel riquadro **Impostazioni invito Guest** , verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-118">In the **Guest invite settings** pane, ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
5. <span data-ttu-id="37b8e-119">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="37b8e-120">Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** .</span><span class="sxs-lookup"><span data-stu-id="37b8e-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="37b8e-121">Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="37b8e-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="37b8e-122">Se si lavora con clienti provenienti da più organizzazioni, è possibile che si desideri limitare la possibilità di accedere ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="37b8e-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="37b8e-123">Ciò impedirà loro di vedere chi altro è un ospite nella directory.</span><span class="sxs-lookup"><span data-stu-id="37b8e-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="37b8e-124">Per eseguire questa operazione, in **restrizioni di accesso degli utenti Guest**, selezionare **Guest gli utenti hanno accesso limitato alle proprietà e l'appartenenza delle impostazioni degli oggetti directory** o **l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti directory**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="37b8e-125">Microsoft 365 groups Guest Settings</span><span class="sxs-lookup"><span data-stu-id="37b8e-125">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="37b8e-126">I siti di SharePoint moderni utilizzano i gruppi di Microsoft 365 per controllare l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="37b8e-126">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="37b8e-127">È necessario che le impostazioni Guest dei gruppi Microsoft 365 siano attivate affinché l'accesso guest in siti di SharePoint funzioni.</span><span class="sxs-lookup"><span data-stu-id="37b8e-127">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="37b8e-129">Per impostare Microsoft 365 groups Guest Settings</span><span class="sxs-lookup"><span data-stu-id="37b8e-129">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="37b8e-130">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, espandere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-130">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="37b8e-131">Fare clic su **servizi & componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="37b8e-131">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="37b8e-132">Nell'elenco, fare clic su **gruppi Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-132">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="37b8e-133">Verificare che i membri del gruppo Consenti al di **fuori dell'organizzazione accedano al contenuto del gruppo** e che i proprietari del **gruppo aggiungano persone all'esterno dell'organizzazione ai gruppi di caselle di** controllo siano entrambe controllate.</span><span class="sxs-lookup"><span data-stu-id="37b8e-133">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="37b8e-134">Se sono state apportate modifiche, fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-134">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="37b8e-135">Impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="37b8e-135">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="37b8e-136">Affinché gli utenti dispongano dell'accesso ai siti di SharePoint, le impostazioni di condivisione a livello dell'organizzazione di SharePoint devono consentire la condivisione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="37b8e-136">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="37b8e-137">Le impostazioni a livello di organizzazione determinano le impostazioni disponibili per i singoli siti.</span><span class="sxs-lookup"><span data-stu-id="37b8e-137">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="37b8e-138">Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="37b8e-138">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="37b8e-139">Se si desidera consentire la condivisione di file e cartelle non autenticata, scegliere **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-139">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="37b8e-140">Se si desidera garantire che tutti gli utenti esterni all'organizzazione debbano eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-140">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="37b8e-141">Scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="37b8e-141">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="37b8e-143">Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="37b8e-143">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="37b8e-144">Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento a sinistra, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-144">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="37b8e-145">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-145">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="37b8e-146">Assicurarsi che la condivisione esterna per SharePoint sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-146">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="37b8e-147">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-147">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="37b8e-148">Creare un sito</span><span class="sxs-lookup"><span data-stu-id="37b8e-148">Create a site</span></span>

<span data-ttu-id="37b8e-149">Il passaggio successivo consiste nel creare il sito che si intende utilizzare per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="37b8e-149">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="37b8e-150">Per creare un sito</span><span class="sxs-lookup"><span data-stu-id="37b8e-150">To create a site</span></span>
1. <span data-ttu-id="37b8e-151">Nell'interfaccia di amministrazione di SharePoint, in **Siti** fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-151">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="37b8e-152">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-152">Click **Create**.</span></span>
3. <span data-ttu-id="37b8e-153">Fare clic su **sito del team**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-153">Click **Team site**.</span></span>
4. <span data-ttu-id="37b8e-154">Digitare il nome di un sito e immettere un nome per il proprietario del gruppo (proprietario del sito).</span><span class="sxs-lookup"><span data-stu-id="37b8e-154">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="37b8e-155">In **Impostazioni avanzate**scegliere se si desidera che sia un sito pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="37b8e-155">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="37b8e-156">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-156">Click **Next**.</span></span>
7. <span data-ttu-id="37b8e-157">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-157">Click **Finish**.</span></span>

<span data-ttu-id="37b8e-158">Gli utenti verranno invitati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="37b8e-158">We'll invite users later.</span></span> <span data-ttu-id="37b8e-159">Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito.</span><span class="sxs-lookup"><span data-stu-id="37b8e-159">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="37b8e-160">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="37b8e-160">SharePoint site level sharing settings</span></span>

<span data-ttu-id="37b8e-161">Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il sito.</span><span class="sxs-lookup"><span data-stu-id="37b8e-161">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="37b8e-162">Ad esempio, se si impostano le impostazioni a livello di organizzazione per tutti gli **utenti**, ma si desidera che tutti gli ospiti eseguano l'autenticazione per questo sito, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su **ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-162">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="37b8e-163">Si noti che il sito non può essere condiviso con persone non autenticate (impostazione di**tutti** gli utenti), ma è possibile eseguire singoli file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="37b8e-163">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="37b8e-165">Per impostare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="37b8e-165">To set site-level sharing settings</span></span>
1. <span data-ttu-id="37b8e-166">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-166">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="37b8e-167">Selezionare il sito appena creato.</span><span class="sxs-lookup"><span data-stu-id="37b8e-167">Select the site that you just created.</span></span>
3. <span data-ttu-id="37b8e-168">Sulla barra multifunzione fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-168">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="37b8e-169">Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-169">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="37b8e-170">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-170">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="37b8e-171">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="37b8e-171">Invite users</span></span>

<span data-ttu-id="37b8e-172">Le impostazioni di condivisione Guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e ospiti al sito.</span><span class="sxs-lookup"><span data-stu-id="37b8e-172">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="37b8e-173">L'accesso al sito è controllato tramite il gruppo Microsoft 365 associato, quindi verranno aggiunti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="37b8e-173">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="37b8e-174">Per invitare gli utenti interni a un gruppo</span><span class="sxs-lookup"><span data-stu-id="37b8e-174">To invite internal users to a group</span></span>
1. <span data-ttu-id="37b8e-175">Passare al sito in cui si desidera aggiungere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="37b8e-175">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="37b8e-176">Fare clic su **membri** in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="37b8e-176">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="37b8e-177">Fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-177">Click **Add members**.</span></span>
4. <span data-ttu-id="37b8e-178">Digitare i nomi o gli indirizzi di posta elettronica degli utenti che si desidera invitare al sito e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-178">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="37b8e-179">Gli utenti guest non possono essere aggiunti dal sito.</span><span class="sxs-lookup"><span data-stu-id="37b8e-179">Guest users can't be added from the site.</span></span> <span data-ttu-id="37b8e-180">È necessario aggiungerli utilizzando Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="37b8e-180">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="37b8e-181">Per invitare gli ospiti a un gruppo</span><span class="sxs-lookup"><span data-stu-id="37b8e-181">To invite guests to a group</span></span>
1. <span data-ttu-id="37b8e-182">In **gruppi**, in Outlook sul Web, fare clic sul gruppo in cui si desidera aggiungere i membri.</span><span class="sxs-lookup"><span data-stu-id="37b8e-182">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="37b8e-183">Aprire la scheda contatto di gruppo e quindi, in **altre opzioni** (...), fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-183">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="37b8e-184">Digitare gli indirizzi di posta elettronica degli utenti che si desidera invitare e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-184">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="37b8e-185">Scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="37b8e-185">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="37b8e-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37b8e-186">See Also</span></span>

[<span data-ttu-id="37b8e-187">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="37b8e-187">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="37b8e-188">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="37b8e-188">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="37b8e-189">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="37b8e-189">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="37b8e-190">[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="37b8e-190">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>
