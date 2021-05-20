---
title: Collaborare con gli utenti guest a un documento
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
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: In questo articolo imparerai a collaborare con gli utenti guest su un documento in SharePoint e OneDrive.
ms.openlocfilehash: 338c7f32944bccb766ed923c12a9fceee4d81db8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537836"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="5b87d-103">Collaborare con gli utenti guest a un documento</span><span class="sxs-lookup"><span data-stu-id="5b87d-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="5b87d-104">Se è necessario collaborare con persone esterne all'organizzazione sui documenti in SharePoint o OneDrive, è possibile inviare loro un collegamento di condivisione al documento.</span><span class="sxs-lookup"><span data-stu-id="5b87d-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="5b87d-105">In questo articolo verranno descritti i passaggi di configurazione Microsoft 365 necessari per configurare i collegamenti di condivisione per SharePoint e OneDrive per le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b87d-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="5b87d-106">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="5b87d-106">Video demonstration</span></span>

<span data-ttu-id="5b87d-107">Il video mostra la procedura di configurazione descritta in questo documento.</span><span class="sxs-lookup"><span data-stu-id="5b87d-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="5b87d-108">Impostazioni di collaborazione esterna di Azure</span><span class="sxs-lookup"><span data-stu-id="5b87d-108">Azure external collaboration settings</span></span>

<span data-ttu-id="5b87d-109">La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni di collaborazione esterna B2B in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="5b87d-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="5b87d-110">Se la condivisione guest è disabilitata o limitata in Azure AD, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5b87d-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="5b87d-111">Controllare le impostazioni di collaborazione esterna B2B per assicurarsi che la condivisione con gli utenti guest non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="5b87d-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina delle impostazioni di Organizational Relationships di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="5b87d-113">Per configurare le impostazioni di collaborazione esterna.</span><span class="sxs-lookup"><span data-stu-id="5b87d-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="5b87d-114">Accedere ad Azure Active Directory su [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5b87d-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="5b87d-115">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5b87d-116">Fare clic su **Identità esterne**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-116">Click **External identities**.</span></span>
4. <span data-ttu-id="5b87d-117">Nella schermata **Attività iniziali**, nel riquadro di spostamento a sinistra, fare clic su **Impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="5b87d-118">Verificare che le opzioni **Amministratori e utenti con il ruolo di guest possono invitare** e **I membri possono invitare** siano entrambe impostate su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="5b87d-119">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="5b87d-120">Prendere nota delle impostazioni nella sezione **Restrizioni di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="5b87d-121">Verificare che i domini degli utenti guest con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="5b87d-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="5b87d-122">Se si lavora con utenti guest da più organizzazioni, è possibile limitare la possibilità di accesso ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="5b87d-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="5b87d-123">In questo modo, non potranno vedere gli altri utenti guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="5b87d-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="5b87d-124">A questo scopo in **Restrizioni di accesso degli utenti guest**, selezionare **Gli utenti guest hanno accesso limitato alle proprietà e all'iscrizione delle impostazioni degli oggetti della directory** oppure **L'accesso degli utenti guest è limitato alle proprietà e alle iscrizioni dei propri oggetti della directory**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="5b87d-125">SharePoint di condivisione a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="5b87d-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="5b87d-126">Per consentire agli utenti esterni all'organizzazione di accedere a un documento in SharePoint o OneDrive, le impostazioni di condivisione SharePoint e OneDrive a livello di organizzazione devono consentire la condivisione con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b87d-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="5b87d-127">Le impostazioni a livello di organizzazione SharePoint determinare le impostazioni che saranno disponibili per singoli SharePoint siti.</span><span class="sxs-lookup"><span data-stu-id="5b87d-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="5b87d-128">Le impostazioni del sito non possono essere più permissive delle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b87d-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="5b87d-129">L'impostazione a livello di OneDrive determina il livello di condivisione che sarà disponibile nelle raccolte OneDrive utenti.</span><span class="sxs-lookup"><span data-stu-id="5b87d-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="5b87d-130">Per SharePoint e OneDrive, se si desidera consentire la condivisione di file e cartelle non autenticati, scegliere **Chiunque**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="5b87d-131">Se si desidera verificare che gli utenti esterni all'organizzazione devono eseguire l'autenticazione, scegliere **Guest nuovi ed esistenti.**</span><span class="sxs-lookup"><span data-stu-id="5b87d-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="5b87d-132">*I* collegamenti chiunque sono il modo più semplice per condividere: gli utenti esterni all'organizzazione possono aprire il collegamento senza autenticazione e possono passarlo ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="5b87d-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="5b87d-133">Ad SharePoint, scegliere l'impostazione più permissiva che sarà necessaria a qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b87d-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="5b87d-135">Per configurare le impostazioni di condivisione a livello di organizzazione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="5b87d-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="5b87d-136">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft 365, in **Interfacce di amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="5b87d-137">Nel riquadro SharePoint sinistra dell'interfaccia di amministrazione fare clic su Condivisione in **Criteri.**</span><span class="sxs-lookup"><span data-stu-id="5b87d-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="5b87d-138">Verificare che la condivisione esterna SharePoint o OneDrive sia impostata su **Chiunque** o Su Guest **nuovi ed esistenti.**</span><span class="sxs-lookup"><span data-stu-id="5b87d-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="5b87d-139">L'impostazione OneDrive non può essere più permissiva rispetto all'impostazione SharePoint.)</span><span class="sxs-lookup"><span data-stu-id="5b87d-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="5b87d-140">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="5b87d-141">Impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5b87d-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="5b87d-142">Le impostazioni predefinite per i collegamenti a file e cartelle determinano le opzioni di collegamento visualizzate dagli utenti per impostazione predefinita durante la condivisione di un file o una cartella.</span><span class="sxs-lookup"><span data-stu-id="5b87d-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="5b87d-143">Se si desidera, gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima della condivisione.</span><span class="sxs-lookup"><span data-stu-id="5b87d-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="5b87d-144">Tenere presente che questa impostazione influisce SharePoint siti all'interno dell'organizzazione, nonché OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5b87d-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="5b87d-145">Scegliere un collegamento da uno dei tipi seguenti, che viene quindi selezionato per impostazione predefinita quando gli utenti condividono file e cartelle:</span><span class="sxs-lookup"><span data-stu-id="5b87d-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="5b87d-146">**Chiunque abbia il collegamento:** scegliere questa opzione se si prevede di eseguire molte condivisioni di file e cartelle non autenticati.</span><span class="sxs-lookup"><span data-stu-id="5b87d-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="5b87d-147">Se si desidera autorizzare *Chiunque* abbia il collegamento, ma si è preoccupati in caso di condivisione accidentale non autenticata, considerare una delle altre opzioni come predefinite.</span><span class="sxs-lookup"><span data-stu-id="5b87d-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="5b87d-148">Questo tipo di collegamento è disponibile solo se è stata abilitata la condivisione **Chiunque**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="5b87d-149">**Solo gli utenti dell'organizzazione**: scegliere questa opzione se si prevede che la maggior parte delle condivisioni di file e cartelle sia con persone interne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b87d-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="5b87d-150">**Utenti specifici**: valutare questa opzione se si prevede di condividere molti file e cartelle con utenti guest.</span><span class="sxs-lookup"><span data-stu-id="5b87d-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="5b87d-151">Questo tipo di collegamento funziona con gli utenti guest e richiede l'autenticazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="5b87d-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="5b87d-153">Per impostare le impostazioni SharePoint e OneDrive collegamento predefinito a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="5b87d-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="5b87d-154">Passare alla pagina Condivisione nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5b87d-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="5b87d-155">In **Collegamenti a file e cartelle**, selezionare il collegamento di condivisione predefinito che si desidera usare.</span><span class="sxs-lookup"><span data-stu-id="5b87d-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="5b87d-156">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="5b87d-157">Per impostare l'autorizzazione per il collegamento di condivisione, in **Scegliere l'autorizzazione** selezionata per impostazione predefinita per i collegamenti di condivisione.</span><span class="sxs-lookup"><span data-stu-id="5b87d-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="5b87d-158">Selezionare **Visualizza** se non si desidera che gli utenti non autenticati apportare modifiche ai file e alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="5b87d-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="5b87d-159">Selezionare **Modifica** se si desidera consentire agli utenti non autenticati di apportare modifiche ai file e alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="5b87d-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="5b87d-160">Si noti che le due opzioni di premissione precedenti possono essere applicate non solo agli utenti guest/esterni, ma anche agli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="5b87d-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="5b87d-161">L'opzione di autorizzazione scelta è determinata dalla discrezione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5b87d-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="5b87d-162">Per impostare le autorizzazioni per i collegamenti che consentono la condivisione con chiunque</span><span class="sxs-lookup"><span data-stu-id="5b87d-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="5b87d-163">In Questi **collegamenti è possibile assegnare queste autorizzazioni:** riquadro secondario,</span><span class="sxs-lookup"><span data-stu-id="5b87d-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="5b87d-164">**Nell'elenco** a discesa File</span><span class="sxs-lookup"><span data-stu-id="5b87d-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="5b87d-165">Selezionare **Visualizza e modifica** se si desidera consentire agli utenti non autenticati di apportare modifiche ai file.</span><span class="sxs-lookup"><span data-stu-id="5b87d-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="5b87d-166">Selezionare **Visualizza** se non si desidera che gli utenti non autenticati apportare modifiche ai file.</span><span class="sxs-lookup"><span data-stu-id="5b87d-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="5b87d-167">**Nell'elenco a** discesa Cartelle</span><span class="sxs-lookup"><span data-stu-id="5b87d-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="5b87d-168">Selezionare **Visualizza, modifica e carica** se si desidera consentire agli utenti non autenticati di apportare modifiche alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="5b87d-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="5b87d-169">Selezionare **Visualizza** se non si desidera che gli utenti non autenticati apportare modifiche alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="5b87d-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="5b87d-170">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5b87d-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="5b87d-171">Se si condividono file e cartelle presenti in un sito SharePoint, è inoltre necessario controllare le impostazioni di condivisione a livello di sito per tale sito.</span><span class="sxs-lookup"><span data-stu-id="5b87d-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="5b87d-173">Per configurare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="5b87d-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="5b87d-174">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="5b87d-175">Selezionare il sito in cui si desidera condividere file e cartelle con utenti guest.</span><span class="sxs-lookup"><span data-stu-id="5b87d-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="5b87d-176">Scorrere verso destra nella riga (in cui è presente il sito selezionato) e fare clic in un punto qualsiasi della **colonna Condivisione** esterna.</span><span class="sxs-lookup"><span data-stu-id="5b87d-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="5b87d-177">Nella pagina visualizzata fare clic sulla **scheda** Criteri.</span><span class="sxs-lookup"><span data-stu-id="5b87d-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="5b87d-178">Nel riquadro **Condivisione esterna** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="5b87d-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="5b87d-179">Verificare che la condivisione sia impostata su **Chiunque** o **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="5b87d-180">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b87d-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="5b87d-181">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="5b87d-181">Invite users</span></span>

<span data-ttu-id="5b87d-182">Le impostazioni di condivisione guest sono ora configurate. in modo che gli utenti possano ora condividere file e cartelle con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b87d-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="5b87d-183">Per [ulteriori informazioni, vedere](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) Share OneDrive files and folders e [Share SharePoint files or folders.](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)</span><span class="sxs-lookup"><span data-stu-id="5b87d-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b87d-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b87d-184">See also</span></span>

[<span data-ttu-id="5b87d-185">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="5b87d-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="5b87d-186">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="5b87d-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="5b87d-187">Integrazione di SharePoint e OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="5b87d-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)