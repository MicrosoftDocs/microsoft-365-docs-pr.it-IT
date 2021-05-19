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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: Informazioni sui passaggi Microsoft 365 configurazione necessari per configurare un sito SharePoint per la collaborazione con gli utenti guest.
ms.openlocfilehash: f91b9c64dbdca8ed7e3ada3315cb57f1c728f838
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539252"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="ca35a-103">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="ca35a-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="ca35a-104">Se è necessario collaborare con utenti guest tra documenti, dati ed elenchi, è possibile utilizzare un SharePoint sito.</span><span class="sxs-lookup"><span data-stu-id="ca35a-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="ca35a-105">I SharePoint moderni sono connessi ai gruppi Microsoft 365 e possono gestire l'appartenenza al sito e fornire ulteriori strumenti di collaborazione, ad esempio una cassetta postale condivisa e un calendario.</span><span class="sxs-lookup"><span data-stu-id="ca35a-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="ca35a-106">In questo articolo verranno descritti i passaggi Microsoft 365 configurazione necessari per configurare un sito SharePoint per la collaborazione con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="ca35a-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="ca35a-107">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="ca35a-107">Video demonstration</span></span>

<span data-ttu-id="ca35a-108">Il video mostra la procedura di configurazione descritta in questo documento.</span><span class="sxs-lookup"><span data-stu-id="ca35a-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="ca35a-109">Impostazioni di collaborazione esterna di Azure</span><span class="sxs-lookup"><span data-stu-id="ca35a-109">Azure external collaboration settings</span></span>

<span data-ttu-id="ca35a-110">La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni di collaborazione esterna B2B in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="ca35a-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="ca35a-111">Se in Azure AD la condivisione con gli utenti guest è disabilitata o limitata, questa impostazione sovrascrive tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca35a-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="ca35a-112">Controllare le impostazioni di collaborazione esterna B2B per assicurarsi che la condivisione con gli utenti guest non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="ca35a-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina Azure Active Directory collaborazione Impostazioni esterna](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="ca35a-114">Per configurare le impostazioni di collaborazione esterna.</span><span class="sxs-lookup"><span data-stu-id="ca35a-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="ca35a-115">Accedere ad Azure Active Directory su [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="ca35a-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="ca35a-116">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="ca35a-117">Fare clic su **Identità esterne**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-117">Click **External identities**.</span></span>
4. <span data-ttu-id="ca35a-118">Nella schermata **Attività iniziali**, nel riquadro di spostamento a sinistra, fare clic su **Impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="ca35a-119">Verificare che le opzioni **Amministratori e utenti con il ruolo di guest possono invitare** e **I membri possono invitare** siano entrambe impostate su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="ca35a-120">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="ca35a-121">Prendere nota delle impostazioni nella sezione **Restrizioni di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="ca35a-122">Verificare che i domini degli utenti guest con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="ca35a-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="ca35a-123">Se si lavora con utenti guest da più organizzazioni, è possibile limitare la possibilità di accesso ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="ca35a-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="ca35a-124">In questo modo, non potranno vedere gli altri utenti guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="ca35a-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="ca35a-125">A questo scopo in **Restrizioni di accesso degli utenti guest**, selezionare **Gli utenti guest hanno accesso limitato alle proprietà e all'iscrizione delle impostazioni degli oggetti della directory** oppure **L'accesso degli utenti guest è limitato alle proprietà e alle iscrizioni dei propri oggetti della directory**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="ca35a-126">Impostazioni guest di Gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ca35a-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="ca35a-127">I SharePoint moderni utilizzano Microsoft 365 per controllare l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="ca35a-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="ca35a-128">Le Microsoft 365 guest dei gruppi di utenti devono essere attivate per consentire il funzionamento dell'accesso guest nei SharePoint siti.</span><span class="sxs-lookup"><span data-stu-id="ca35a-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="ca35a-130">Per configurare le impostazioni guest di Gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ca35a-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="ca35a-131">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, espandere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="ca35a-132">Fare clic su **Impostazioni organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="ca35a-133">Nell'elenco, fare clic su **Gruppi di Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="ca35a-134">Verificare che le caselle di controllo **Consenti ai proprietari del gruppo di aggiungere persone esterne all'organizzazione ai Gruppi di Microsoft 365 come utenti guest** e **Consenti ai membri del gruppo guest di accedere ai contenuti del gruppo** siano entrambe selezionate.</span><span class="sxs-lookup"><span data-stu-id="ca35a-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="ca35a-135">Se si apportano modifiche, fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="ca35a-136">SharePoint di condivisione a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="ca35a-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="ca35a-137">Per consentire agli utenti guest di accedere SharePoint siti, le impostazioni di condivisione SharePoint a livello di organizzazione devono consentire la condivisione con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="ca35a-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="ca35a-138">Le impostazioni a livello di organizzazione determinano le impostazioni che saranno disponibili per i singoli siti.</span><span class="sxs-lookup"><span data-stu-id="ca35a-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="ca35a-139">Le impostazioni del sito non possono essere più permissive delle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca35a-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="ca35a-140">Se si desidera consentire la condivisione di file e cartelle non autenticati, scegliere **Chiunque**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="ca35a-141">Se si desidera verificare che tutti gli utenti esterni all'organizzazione devono eseguire l'autenticazione, scegliere **Guest nuovi ed esistenti.**</span><span class="sxs-lookup"><span data-stu-id="ca35a-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="ca35a-142">Scegliere l'impostazione più permissiva necessaria a tutti i siti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca35a-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="ca35a-144">Per configurare le impostazioni di condivisione a livello di organizzazione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="ca35a-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="ca35a-145">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, in **Interfacce di amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="ca35a-146">Nel riquadro SharePoint sinistra dell'interfaccia di amministrazione fare clic su Condivisione in **Criteri.**</span><span class="sxs-lookup"><span data-stu-id="ca35a-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="ca35a-147">Assicurarsi che la condivisione esterna per SharePoint sia impostata su **Chiunque** oppure **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="ca35a-148">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="ca35a-149">Creare un sito</span><span class="sxs-lookup"><span data-stu-id="ca35a-149">Create a site</span></span>

<span data-ttu-id="ca35a-150">Il passaggio successivo consiste nel creare il sito che si prevede di utilizzare per collaborare con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="ca35a-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="ca35a-151">Per creare un sito</span><span class="sxs-lookup"><span data-stu-id="ca35a-151">To create a site</span></span>
1. <span data-ttu-id="ca35a-152">Nell'interfaccia di amministrazione di SharePoint, in **Siti** fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="ca35a-153">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-153">Click **Create**.</span></span>
3. <span data-ttu-id="ca35a-154">Fare clic **su Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-154">Click **Team site**.</span></span>
4. <span data-ttu-id="ca35a-155">Digitare un nome di sito e immettere un nome per il proprietario del gruppo (proprietario del sito).</span><span class="sxs-lookup"><span data-stu-id="ca35a-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="ca35a-156">In **Impostazioni avanzate** scegliere se si desidera che il sito sia pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="ca35a-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="ca35a-157">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-157">Click **Next**.</span></span>
7. <span data-ttu-id="ca35a-158">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-158">Click **Finish**.</span></span>

<span data-ttu-id="ca35a-159">In seguito verranno invitato gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ca35a-159">We'll invite users later.</span></span> <span data-ttu-id="ca35a-160">Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per questo sito.</span><span class="sxs-lookup"><span data-stu-id="ca35a-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="ca35a-161">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="ca35a-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="ca35a-162">Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il sito.</span><span class="sxs-lookup"><span data-stu-id="ca35a-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="ca35a-163">Ad esempio, se si impostano le impostazioni a livello di organizzazione su **Chiunque**, ma si desidera che tutti gli utenti guest eseercitino l'autenticazione per il sito, verificare che le impostazioni di condivisione a livello di sito siano impostate su Utenti guest nuovi ed **esistenti.**</span><span class="sxs-lookup"><span data-stu-id="ca35a-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="ca35a-164">Si noti che il sito non può essere condiviso con utenti non autenticati (impostazione **Chiunque),** ma i singoli file e cartelle possono essere condivisi.</span><span class="sxs-lookup"><span data-stu-id="ca35a-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="ca35a-165">È inoltre possibile utilizzare le etichette di riservatezza per controllare le impostazioni di condivisione esterne [per SharePoint siti.](../compliance/sensitivity-labels-teams-groups-sites.md)</span><span class="sxs-lookup"><span data-stu-id="ca35a-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="ca35a-167">Per configurare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="ca35a-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="ca35a-168">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="ca35a-169">Selezionare il sito che si desidera condividere.</span><span class="sxs-lookup"><span data-stu-id="ca35a-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="ca35a-170">Fare clic su ..., quindi su **Condivisione.**</span><span class="sxs-lookup"><span data-stu-id="ca35a-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="ca35a-171">Verificare che la condivisione sia impostata su **Chiunque** o **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="ca35a-172">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="ca35a-173">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="ca35a-173">Invite users</span></span>

<span data-ttu-id="ca35a-174">Le impostazioni di condivisione guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e guest al sito.</span><span class="sxs-lookup"><span data-stu-id="ca35a-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="ca35a-175">L'accesso al sito viene controllato tramite il gruppo Microsoft 365 associato, quindi verranno aggiunti utenti.</span><span class="sxs-lookup"><span data-stu-id="ca35a-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="ca35a-176">Per invitare utenti interni a un gruppo</span><span class="sxs-lookup"><span data-stu-id="ca35a-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="ca35a-177">Passare al sito in cui si desidera aggiungere utenti.</span><span class="sxs-lookup"><span data-stu-id="ca35a-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="ca35a-178">Fare **clic sul** collegamento Membri in alto a destra che indica il numero di membri.</span><span class="sxs-lookup"><span data-stu-id="ca35a-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="ca35a-179">Fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-179">Click **Add members**.</span></span>
4. <span data-ttu-id="ca35a-180">Digitare i nomi o gli indirizzi di posta elettronica degli utenti che si desidera invitare nel sito e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="ca35a-181">Non è possibile aggiungere utenti guest dal sito.</span><span class="sxs-lookup"><span data-stu-id="ca35a-181">Guests can't be added from the site.</span></span> <span data-ttu-id="ca35a-182">È necessario aggiungerli usando Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="ca35a-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="ca35a-183">Pertanto, come prerequisito per aggiungere e invitare utenti guest a un gruppo, fare clic sull'URL del sito nella colonna **URL**  per passare alla pagina specifica del sito.</span><span class="sxs-lookup"><span data-stu-id="ca35a-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="ca35a-184">In questa pagina fai clic **sull'icona di avvio** delle app e seleziona **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="ca35a-185">Questa è la schermata da cui è possibile invitare utenti guest in un gruppo, per la quale la procedura è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="ca35a-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="ca35a-186">Per invitare utenti guest a un gruppo</span><span class="sxs-lookup"><span data-stu-id="ca35a-186">To invite guests to a group</span></span>
1. <span data-ttu-id="ca35a-187">In **Gruppi** fare clic sul gruppo a cui si desidera invitare utenti guest.</span><span class="sxs-lookup"><span data-stu-id="ca35a-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="ca35a-188">Aprire la scheda contatto del gruppo, fare clic **sul** collegamento Membri in alto a destra (il collegamento che indica il numero di membri).</span><span class="sxs-lookup"><span data-stu-id="ca35a-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="ca35a-189">fare **clic su Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-189">click **Add members**.</span></span>
4. <span data-ttu-id="ca35a-190">Digitare gli indirizzi di posta elettronica degli utenti guest che si desidera invitare e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="ca35a-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="ca35a-191">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ca35a-191">Click **Close**.</span></span>
<span data-ttu-id="ca35a-192">Tenere presente che  è necessario fare clic su Chiudi solo se non si è proprietari del gruppo e, di conseguenza, non è consentito aggiungere il guest al gruppo.</span><span class="sxs-lookup"><span data-stu-id="ca35a-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="ca35a-193">In questi casi, la richiesta di aggiungere il guest al gruppo viene trasferita al proprietario del gruppo per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="ca35a-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca35a-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca35a-194">See also</span></span>

[<span data-ttu-id="ca35a-195">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="ca35a-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="ca35a-196">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="ca35a-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="ca35a-197">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="ca35a-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="ca35a-198">[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="ca35a-198">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

[<span data-ttu-id="ca35a-199">Integrazione di SharePoint e OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="ca35a-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)