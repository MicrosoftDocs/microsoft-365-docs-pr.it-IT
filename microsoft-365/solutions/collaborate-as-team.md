---
title: Collaborazione con gli utenti guest in un team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
localization_priority: Priority
f1.keywords: NOCSH
description: Informazioni sulla procedura di configurazione di Microsoft 365 necessaria per consentire a un team di comunicare, collaborare ad attività e documenti con utenti guest in Teams.
ms.openlocfilehash: 4e734af198563d0bc4599b4476b3823384989212
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904661"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="c2b6d-103">Collaborazione con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="c2b6d-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="c2b6d-104">Se occorre collaborare con utenti guest a documenti e attività e comunicare, è consigliabile usare Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="c2b6d-105">Teams offre tutte le funzionalità di collaborazione disponibili in Office e SharePoint con una chat persistente e un set personalizzabile ed estendibile di strumenti di collaborazione in un'esperienza utente unificata.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="c2b6d-106">Questo articolo illustra la procedura di configurazione di Microsoft 365 necessaria per consentire a un team di collaborare con utenti guest.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="c2b6d-107">Dopo aver configurato l'accesso agli utenti guest, è possibile invitarli ai team seguendo la procedura descritta in [Aggiungere utenti guest a un team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="c2b6d-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="c2b6d-108">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="c2b6d-108">Video demonstration</span></span>

<span data-ttu-id="c2b6d-109">Il video mostra la procedura di configurazione descritta in questo documento.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="c2b6d-110">Impostazioni di collaborazione esterna di Azure</span><span class="sxs-lookup"><span data-stu-id="c2b6d-110">Azure External collaboration settings</span></span>

<span data-ttu-id="c2b6d-111">La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni di collaborazione esterna B2B in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="c2b6d-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="c2b6d-112">Se in Azure AD la condivisione con gli utenti guest è disabilitata o limitata, questa impostazione sovrascrive tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="c2b6d-113">Controllare le impostazioni di collaborazione esterna B2B per assicurarsi che la condivisione con gli utenti guest non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina delle impostazioni di Organizational Relationships di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="c2b6d-115">Per configurare le impostazioni di collaborazione esterna.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="c2b6d-116">Accedere ad Azure Active Directory su [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c2b6d-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="c2b6d-117">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="c2b6d-118">Fare clic su **Identità esterne**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-118">Click **External identities**.</span></span>
4. <span data-ttu-id="c2b6d-119">Nella schermata **Attività iniziali**, nel riquadro di spostamento a sinistra, fare clic su **Impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="c2b6d-120">Verificare che le opzioni **Amministratori e utenti con il ruolo di guest possono invitare** e **I membri possono invitare** siano entrambe impostate su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="c2b6d-121">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="c2b6d-122">Prendere nota delle impostazioni nella sezione **Restrizioni di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="c2b6d-123">Verificare che i domini degli utenti guest con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="c2b6d-124">Se si lavora con utenti guest da più organizzazioni, è possibile limitare la possibilità di accesso ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="c2b6d-125">In questo modo, non potranno vedere gli altri utenti guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="c2b6d-126">A questo scopo in **Restrizioni di accesso degli utenti guest**, selezionare **Gli utenti guest hanno accesso limitato alle proprietà e all'iscrizione delle impostazioni degli oggetti della directory** oppure **L'accesso degli utenti guest è limitato alle proprietà e alle iscrizioni dei propri oggetti della directory**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="c2b6d-127">Impostazioni di accesso degli utenti guest</span><span class="sxs-lookup"><span data-stu-id="c2b6d-127">Teams guest access settings</span></span>

<span data-ttu-id="c2b6d-128">Teams ha un interruttore principale Attivato/Disattivato per l'accesso degli utenti guest e una varietà di impostazioni disponibili per controllare le operazioni che gli utenti guest possono eseguire in un team.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="c2b6d-129">L'interruttore principale **Consenti accesso ospite in Teams** deve essere **Attivato** perché l'accesso guest funzioni in Teams.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="c2b6d-130">Verificare che l'accesso guest sia abilitato in Teams e apportare eventuali modifiche alle impostazioni in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="c2b6d-131">Tenere presente che le impostazioni influiscono su tutti i team.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-131">Keep in mind that these settings affect all teams.</span></span>

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="c2b6d-133">Per configurare le impostazioni di accesso guest di Teams</span><span class="sxs-lookup"><span data-stu-id="c2b6d-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="c2b6d-134">Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c2b6d-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="c2b6d-135">Nel riquadro di spostamento a sinistra, fare clic su **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="c2b6d-136">In **Interfacce di amministrazione**, fare clic su **Teams**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="c2b6d-137">Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** nel riquadro di spostamento a sinistra e fare clic su **Accesso guest**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="c2b6d-138">Assicurarsi che l'opzione **Consenti accesso ospite in Teams** sia \*\*\*\* abilitata.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="c2b6d-139">Apportare le modifiche desiderate alle impostazioni guest aggiuntive e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="c2b6d-140">Dopo aver attivato l'accesso guest in Teams, è possibile controllare in modo facoltativo l'accesso guest a singoli team e relativi siti di SharePoint associati usando etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="c2b6d-141">Per altre informazioni, vedere [Usare le etichette di riservatezza per proteggere i contenuti in Microsoft Teams, Gruppi di Microsoft 365 e nei siti di SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="c2b6d-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c2b6d-142">Dopo l'attivazione, potrebbero essere necessarie fino a 24 ore prima che le impostazioni guest di Teams diventino effettive.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="c2b6d-143">Impostazioni guest di Gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2b6d-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="c2b6d-144">Teams usa Gruppi di Microsoft 365 per l'iscrizione al team.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="c2b6d-145">Per il funzionamento dell'accesso degli utenti guest in Teams, è necessario che le impostazioni guest di Gruppi di Microsoft 365 siano attivate.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="c2b6d-147">Per configurare le impostazioni guest di Gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2b6d-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="c2b6d-148">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, espandere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="c2b6d-149">Fare clic su **Impostazioni organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="c2b6d-150">Nell'elenco, fare clic su **Gruppi di Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="c2b6d-151">Verificare che le caselle di controllo **Consenti ai proprietari del gruppo di aggiungere persone esterne all'organizzazione ai Gruppi di Microsoft 365 come utenti guest** e **Consenti ai membri del gruppo guest di accedere ai contenuti del gruppo** siano entrambe selezionate.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="c2b6d-152">Se si apportano modifiche, fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="c2b6d-153">Impostazioni di condivisione a livello di organizzazione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="c2b6d-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="c2b6d-154">I contenuti dei team, ad esempio file, cartelle ed elenchi, sono tutti archiviati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="c2b6d-155">Per consentire ai guest di accedere a questi elementi in Teams, le impostazioni di condivisione a livello di organizzazione in SharePoint devono consentire la condivisione con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="c2b6d-156">Le impostazioni a livello di organizzazione determinano quali impostazioni sono disponibili per i singoli siti, tra cui i siti associati ai team.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="c2b6d-157">Le impostazioni del sito non possono essere più permissive delle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="c2b6d-158">Se si vuole consentire la condivisione di file e cartelle con utenti non autenticati, scegliere **Chiunque**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="c2b6d-159">Per assicurarsi che tutti gli utenti guest siano autenticati, scegliere **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="c2b6d-160">Scegliere l'impostazione più permissiva necessaria a tutti i siti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="c2b6d-162">Per configurare le impostazioni di condivisione a livello di organizzazione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="c2b6d-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="c2b6d-163">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, in **Interfacce di amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="c2b6d-164">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Criteri** poi fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="c2b6d-165">Assicurarsi che la condivisione esterna per SharePoint sia impostata su **Chiunque** oppure **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="c2b6d-166">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="c2b6d-167">Impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c2b6d-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="c2b6d-168">Le impostazioni predefinite per i collegamenti a file e cartelle determinano le opzioni di collegamento visualizzate dagli utenti per impostazione predefinita durante la condivisione di un file o una cartella.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="c2b6d-169">Se si desidera, gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima della condivisione.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="c2b6d-170">Tenere presente che questa impostazione influisce su tutti i team e i siti di SharePoint dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="c2b6d-171">Scegliere uno dei tipi di collegamento seguenti, selezionato per impostazione predefinita, quando gli utenti condividono file e cartelle:</span><span class="sxs-lookup"><span data-stu-id="c2b6d-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="c2b6d-172">**Chiunque abbia il collegamento**: scegliere questa opzione se si prevede di eseguire molte condivisioni non autenticate di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="c2b6d-173">Se si desidera autorizzare *Chiunque* abbia il collegamento, ma si è preoccupati in caso di condivisione accidentale non autenticata, considerare una delle altre opzioni come predefinite.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="c2b6d-174">Questo tipo di collegamento è disponibile solo se è stata abilitata la condivisione **Chiunque**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="c2b6d-175">**Solo gli utenti dell'organizzazione**: scegliere questa opzione se si prevede che la maggior parte delle condivisioni di file e cartelle sia con persone interne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="c2b6d-176">**Utenti specifici**: valutare questa opzione se si prevede di condividere molti file e cartelle con utenti guest.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="c2b6d-177">Questo tipo di collegamento funziona con gli utenti guest e richiede l'autenticazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="c2b6d-179">Per configurare le impostazioni dei collegamenti predefiniti a livello di organizzazione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="c2b6d-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="c2b6d-180">Passare alla pagina Condivisione nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="c2b6d-181">In **Collegamenti a file e cartelle**, selezionare il collegamento di condivisione predefinito che si desidera usare.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="c2b6d-182">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="c2b6d-183">Creazione di un team</span><span class="sxs-lookup"><span data-stu-id="c2b6d-183">Create a team</span></span>

<span data-ttu-id="c2b6d-184">Il passaggio successivo consiste nel creare il team che si prevede di usare per collaborare con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="c2b6d-185">Per creare un team</span><span class="sxs-lookup"><span data-stu-id="c2b6d-185">To create a team</span></span>
1. <span data-ttu-id="c2b6d-186">In Teams, nella scheda **Teams**, fare clic su **Partecipa o crea un team** nella parte inferiore del riquadro a sinistra.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="c2b6d-187">Fare clic su **Crea team**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="c2b6d-188">Fare clic su **Creare un team da zero**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="c2b6d-189">Scegliere **Privato** o **Pubblico**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="c2b6d-190">Digitare un nome e una descrizione per il team e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="c2b6d-191">Fare clic **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-191">Click **Skip**.</span></span>

<span data-ttu-id="c2b6d-192">In seguito verranno invitato gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-192">We'll invite users later.</span></span> <span data-ttu-id="c2b6d-193">È quindi importante controllare le impostazioni di condivisione a livello di sito per il sito di SharePoint associato al team.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="c2b6d-194">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c2b6d-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="c2b6d-195">Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il team.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="c2b6d-196">Ad esempio, se si configurano le impostazioni a livello di organizzazione su **Chiunque**, ma si vuole che tutti gli utenti guest siano autenticati per accedere al team, verificare che le impostazioni di condivisione a livello di sito siano impostate su **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="c2b6d-198">Per configurare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="c2b6d-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="c2b6d-199">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="c2b6d-200">Selezionare il sito del team appena creato.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="c2b6d-201">Fare clic su ... e scegliere **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="c2b6d-202">Verificare che la condivisione sia impostata su **Chiunque** o **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="c2b6d-203">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="c2b6d-204">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="c2b6d-204">Invite users</span></span>

<span data-ttu-id="c2b6d-205">Le impostazioni di condivisione guest sono ora configurate, quindi è possibile iniziare ad aggiungere gli utenti interni e quelli guest al team.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="c2b6d-206">Per invitare utenti interni a un team</span><span class="sxs-lookup"><span data-stu-id="c2b6d-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="c2b6d-207">Nel team, fare clic su **Altre opzioni** (**\*\*\***) e quindi su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="c2b6d-208">Digitare il nome dell'utente da invitare.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="c2b6d-209">Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="c2b6d-210">Per invitare utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="c2b6d-210">To invite guests to a team</span></span>
1. <span data-ttu-id="c2b6d-211">Nel team, fare clic su **Altre opzioni** (**\*\*\***) e quindi su **Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="c2b6d-212">Digitare l'indirizzo di posta elettronica dell'utente guest che si vuole invitare.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="c2b6d-213">Fare clic su **Modifica le informazioni relative agli utenti guest**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="c2b6d-214">Digitare il nome completo dell'utente guest e fare clic sul segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="c2b6d-215">Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c2b6d-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2b6d-216">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2b6d-216">See also</span></span>

[<span data-ttu-id="c2b6d-217">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="c2b6d-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="c2b6d-218">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="c2b6d-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="c2b6d-219">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="c2b6d-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="c2b6d-220">[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="c2b6d-220">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

[<span data-ttu-id="c2b6d-221">Integrazione di SharePoint e OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="c2b6d-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="c2b6d-222">Le opzioni di condivisione sono disattivate quando si condivide da SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="c2b6d-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)