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
description: Informazioni sui passaggi di configurazione di Microsoft 365 necessari per configurare un sito di SharePoint per la collaborazione con gli utenti.
ms.openlocfilehash: df9068ef4b4eb35f946b78d8f7fefa01c254c79c
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029994"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="6dfc5-103">Collaborare con gli utenti guest a un sito</span><span class="sxs-lookup"><span data-stu-id="6dfc5-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="6dfc5-104">Se è necessario collaborare con gli utenti tra documenti, dati ed elenchi, è possibile utilizzare un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="6dfc5-105">I siti di SharePoint moderni sono connessi ai gruppi di Microsoft 365 e possono gestire l'appartenenza al sito e fornire strumenti di collaborazione aggiuntivi quali una cassetta postale condivisa e un calendario.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="6dfc5-106">In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare un sito di SharePoint per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="6dfc5-107">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="6dfc5-107">Video demonstration</span></span>

<span data-ttu-id="6dfc5-108">In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="6dfc5-109">Impostazioni di collaborazione esterna di Azure</span><span class="sxs-lookup"><span data-stu-id="6dfc5-109">Azure external collaboration settings</span></span>

<span data-ttu-id="6dfc5-110">La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni delle relazioni organizzative in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="6dfc5-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="6dfc5-111">Se la condivisione Guest è disabilitata o limitata in Azure AD, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="6dfc5-112">Controllare le impostazioni di collaborazione esterna per assicurarsi che la condivisione con gli ospiti non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Schermata della pagina impostazioni di collaborazione esterna di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="6dfc5-114">Per impostare le impostazioni di collaborazione esterna</span><span class="sxs-lookup"><span data-stu-id="6dfc5-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="6dfc5-115">Accedere a Azure Active Directory all'indirizzo [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="6dfc5-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="6dfc5-116">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="6dfc5-117">Fare clic su **identità esterne**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-117">Click **External identities**.</span></span>
4. <span data-ttu-id="6dfc5-118">Nella schermata **inizia** , nel riquadro di spostamento a sinistra, fare clic su **impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="6dfc5-119">Verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="6dfc5-120">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="6dfc5-121">Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** .</span><span class="sxs-lookup"><span data-stu-id="6dfc5-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="6dfc5-122">Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="6dfc5-123">Se si lavora con clienti provenienti da più organizzazioni, è possibile che si desideri limitare la possibilità di accedere ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="6dfc5-124">Ciò impedirà loro di vedere chi altro è un ospite nella directory.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="6dfc5-125">Per eseguire questa operazione, in **restrizioni di accesso degli utenti Guest** , selezionare **Guest gli utenti hanno accesso limitato alle proprietà e l'appartenenza delle impostazioni degli oggetti directory** o **l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti directory**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-125">To do this, under **Guest user access restrictions** , select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="6dfc5-126">Microsoft 365 groups Guest Settings</span><span class="sxs-lookup"><span data-stu-id="6dfc5-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="6dfc5-127">I siti di SharePoint moderni utilizzano i gruppi di Microsoft 365 per controllare l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="6dfc5-128">È necessario che le impostazioni Guest dei gruppi Microsoft 365 siano attivate affinché l'accesso guest in siti di SharePoint funzioni.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="6dfc5-130">Per impostare Microsoft 365 groups Guest Settings</span><span class="sxs-lookup"><span data-stu-id="6dfc5-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="6dfc5-131">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, espandere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="6dfc5-132">Fare clic su **Impostazioni organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="6dfc5-133">Nell'elenco, fare clic su **gruppi Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="6dfc5-134">Assicurarsi che i **proprietari di Let Group aggiungano le persone all'esterno dell'organizzazione ai gruppi di Microsoft 365 come ospiti** e che i **membri del gruppo di accesso al contenuto del** gruppo siano entrambi controllati.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="6dfc5-135">Se sono state apportate modifiche, fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="6dfc5-136">Impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="6dfc5-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="6dfc5-137">Affinché gli utenti dispongano dell'accesso ai siti di SharePoint, le impostazioni di condivisione a livello dell'organizzazione di SharePoint devono consentire la condivisione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="6dfc5-138">Le impostazioni a livello di organizzazione determinano le impostazioni che saranno disponibili per i singoli siti.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="6dfc5-139">Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="6dfc5-140">Se si desidera consentire la condivisione di file e cartelle non autenticata, scegliere **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="6dfc5-141">Se si desidera garantire che tutti gli utenti esterni all'organizzazione debbano eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="6dfc5-142">Scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="6dfc5-144">Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="6dfc5-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="6dfc5-145">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, in interfaccia di **Amministrazione** , fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers** , click **SharePoint**.</span></span>
2. <span data-ttu-id="6dfc5-146">Nell'interfaccia di amministrazione di SharePoint, nel riquadro di spostamento a sinistra, in **criteri** fare clic su **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-146">In the SharePoint admin center, in the left navigation pane, under **Policies** , click **Sharing**.</span></span>
3. <span data-ttu-id="6dfc5-147">Assicurarsi che la condivisione esterna per SharePoint sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="6dfc5-148">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="6dfc5-149">Creare un sito</span><span class="sxs-lookup"><span data-stu-id="6dfc5-149">Create a site</span></span>

<span data-ttu-id="6dfc5-150">Il passaggio successivo consiste nel creare il sito che si intende utilizzare per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="6dfc5-151">Per creare un sito</span><span class="sxs-lookup"><span data-stu-id="6dfc5-151">To create a site</span></span>
1. <span data-ttu-id="6dfc5-152">Nell'interfaccia di amministrazione di SharePoint, in **Siti** fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-152">In the SharePoint admin center, under **Sites** , click **Active sites**.</span></span>
2. <span data-ttu-id="6dfc5-153">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-153">Click **Create**.</span></span>
3. <span data-ttu-id="6dfc5-154">Fare clic su **sito del team**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-154">Click **Team site**.</span></span>
4. <span data-ttu-id="6dfc5-155">Digitare il nome di un sito e immettere un nome per il proprietario del gruppo (proprietario del sito).</span><span class="sxs-lookup"><span data-stu-id="6dfc5-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="6dfc5-156">In **Impostazioni avanzate** scegliere se si desidera che il sito sia pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-156">Under **Advanced settings** , choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="6dfc5-157">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-157">Click **Next**.</span></span>
7. <span data-ttu-id="6dfc5-158">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-158">Click **Finish**.</span></span>

<span data-ttu-id="6dfc5-159">Gli utenti verranno invitati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-159">We'll invite users later.</span></span> <span data-ttu-id="6dfc5-160">Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="6dfc5-161">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="6dfc5-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="6dfc5-162">Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il sito.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="6dfc5-163">Ad esempio, se si impostano le impostazioni a livello di organizzazione per tutti gli **utenti** , ma si desidera che tutti gli ospiti eseguano l'autenticazione per questo sito, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su **ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-163">For example, if you set the organization-level settings to **Anyone** , but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="6dfc5-164">Si noti che il sito non può essere condiviso con persone non autenticate (impostazione di **tutti** gli utenti), ma è possibile eseguire singoli file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-164">Note that the site cannot be shared with unauthenticated people ( **Anyone** setting), but individual files and folders can.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="6dfc5-166">Per impostare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="6dfc5-166">To set site-level sharing settings</span></span>
1. <span data-ttu-id="6dfc5-167">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-167">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="6dfc5-168">Selezionare il sito che si desidera condividere.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-168">Select the site that you want to share.</span></span>
3. <span data-ttu-id="6dfc5-169">Fare clic su... e fare clic su **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-169">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="6dfc5-170">Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-170">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="6dfc5-171">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-171">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="6dfc5-172">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="6dfc5-172">Invite users</span></span>

<span data-ttu-id="6dfc5-173">Le impostazioni di condivisione Guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e ospiti al sito.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-173">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="6dfc5-174">L'accesso al sito è controllato tramite il gruppo Microsoft 365 associato, quindi verranno aggiunti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-174">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="6dfc5-175">Per invitare gli utenti interni a un gruppo</span><span class="sxs-lookup"><span data-stu-id="6dfc5-175">To invite internal users to a group</span></span>
1. <span data-ttu-id="6dfc5-176">Passare al sito in cui si desidera aggiungere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-176">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="6dfc5-177">Fare clic su collegamento **membri** nell'angolo in alto a destra che indica il numero di membri.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-177">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="6dfc5-178">Fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-178">Click **Add members**.</span></span>
4. <span data-ttu-id="6dfc5-179">Digitare i nomi o gli indirizzi di posta elettronica degli utenti che si desidera invitare al sito e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-179">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="6dfc5-180">Gli utenti guest non possono essere aggiunti dal sito.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-180">Guest users can't be added from the site.</span></span> <span data-ttu-id="6dfc5-181">È necessario aggiungerli utilizzando Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-181">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="6dfc5-182">Pertanto, come prerequisito per aggiungere e invitare gli utenti a un gruppo, fare clic sull'URL del sito nella colonna **URL**  per passare alla pagina specifica del sito.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-182">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="6dfc5-183">Da questa pagina, fare clic sull'icona di **avvio delle app** e selezionare **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-183">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="6dfc5-184">Questa è la schermata dalla quale è possibile invitare gli utenti a un gruppo, per la procedura descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-184">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="6dfc5-185">Per invitare gli ospiti a un gruppo</span><span class="sxs-lookup"><span data-stu-id="6dfc5-185">To invite guests to a group</span></span>
1. <span data-ttu-id="6dfc5-186">In **gruppi** fare clic sul gruppo a cui si desidera invitare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-186">Under **Groups** , click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="6dfc5-187">Aprire la scheda contatto di gruppo, fare clic su collegamenti **membri** in alto a destra, ovvero il collegamento che indica il numero di membri.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-187">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="6dfc5-188">fare clic su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-188">click **Add members**.</span></span>
4. <span data-ttu-id="6dfc5-189">Digitare gli indirizzi di posta elettronica degli utenti che si desidera invitare e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-189">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="6dfc5-190">Scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-190">Click **Close**.</span></span>
<span data-ttu-id="6dfc5-191">Tenere presente che è necessario fare clic su **Chiudi** solo se non si è il proprietario del gruppo e, di conseguenza, non è consentito aggiungere l'ospite all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-191">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="6dfc5-192">In tal caso, la richiesta di aggiungere l'ospite nel gruppo viene trasferita al proprietario del gruppo per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-192">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dfc5-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6dfc5-193">See also</span></span>

[<span data-ttu-id="6dfc5-194">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="6dfc5-194">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="6dfc5-195">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="6dfc5-195">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="6dfc5-196">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="6dfc5-196">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="6dfc5-197">[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="6dfc5-197">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

[<span data-ttu-id="6dfc5-198">Integrazione di SharePoint e OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="6dfc5-198">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
