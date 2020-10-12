---
title: Collaborare con gli utenti guest a un documento
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
description: In questo articolo vengono fornite informazioni su come collaborare con gli utenti di un documento in SharePoint e OneDrive.
ms.openlocfilehash: 022811be642a79c07c632cefcc67a27f19e3af4f
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422606"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="a076c-103">Collaborare con gli utenti guest a un documento</span><span class="sxs-lookup"><span data-stu-id="a076c-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="a076c-104">Se è necessario collaborare con utenti esterni all'organizzazione per documenti in SharePoint o OneDrive, è possibile inviare un collegamento di condivisione al documento.</span><span class="sxs-lookup"><span data-stu-id="a076c-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="a076c-105">In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare i collegamenti di condivisione per SharePoint e OneDrive per le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a076c-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a076c-106">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="a076c-106">Video demonstration</span></span>

<span data-ttu-id="a076c-107">In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="a076c-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="a076c-108">Impostazioni delle relazioni organizzative di Azure</span><span class="sxs-lookup"><span data-stu-id="a076c-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="a076c-109">La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni delle relazioni organizzative in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="a076c-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="a076c-110">Se la condivisione degli ospiti è disabilitata o limitata in Azure Active Directory, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a076c-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="a076c-111">Controllare le impostazioni delle relazioni organizzative per garantire che la condivisione con gli ospiti non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="a076c-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="a076c-113">Per impostare le impostazioni delle relazioni organizzative</span><span class="sxs-lookup"><span data-stu-id="a076c-113">To set organizational relationship settings</span></span>

<span data-ttu-id="a076c-114">Per impostare le impostazioni di collaborazione esterna</span><span class="sxs-lookup"><span data-stu-id="a076c-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="a076c-115">Accedere a Azure Active Directory all'indirizzo [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="a076c-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="a076c-116">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a076c-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="a076c-117">Fare clic su **identità esterne**.</span><span class="sxs-lookup"><span data-stu-id="a076c-117">Click **External identities**.</span></span>
4. <span data-ttu-id="a076c-118">Nella schermata **inizia** , nel riquadro di spostamento a sinistra, fare clic su **impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="a076c-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="a076c-119">Verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a076c-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="a076c-120">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a076c-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="a076c-121">Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** .</span><span class="sxs-lookup"><span data-stu-id="a076c-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="a076c-122">Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="a076c-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="a076c-123">Se si lavora con clienti provenienti da più organizzazioni, è possibile che si desideri limitare la possibilità di accedere ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="a076c-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="a076c-124">Ciò impedirà loro di vedere chi altro è un ospite nella directory.</span><span class="sxs-lookup"><span data-stu-id="a076c-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="a076c-125">Per eseguire questa operazione, in **restrizioni di accesso degli utenti Guest**, selezionare **Guest gli utenti hanno accesso limitato alle proprietà e l'appartenenza delle impostazioni degli oggetti directory** o **l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti directory**.</span><span class="sxs-lookup"><span data-stu-id="a076c-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="a076c-126">Impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a076c-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="a076c-127">Affinché gli utenti esterni all'organizzazione abbiano accesso a un documento in SharePoint o OneDrive, le impostazioni di condivisione a livello di organizzazione di SharePoint e OneDrive devono consentire la condivisione con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a076c-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="a076c-128">Le impostazioni a livello di organizzazione per SharePoint determinano le impostazioni che saranno disponibili per i singoli siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a076c-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="a076c-129">Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a076c-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="a076c-130">L'impostazione a livello di organizzazione per OneDrive determina il livello di condivisione che sarà disponibile nelle raccolte OneDrive degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a076c-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="a076c-131">Per SharePoint e OneDrive, se si desidera consentire la condivisione di file e cartelle non autenticata, scegliere **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="a076c-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="a076c-132">Se si desidera garantire che gli utenti esterni all'organizzazione debbano eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="a076c-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="a076c-133">Collegamenti *chiunque* è il modo più semplice per condividere: gli utenti esterni all'organizzazione possono aprire il collegamento senza l'autenticazione e sono liberi di passarlo ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="a076c-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="a076c-134">Per SharePoint, scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a076c-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="a076c-136">Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a076c-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="a076c-137">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a076c-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="a076c-138">Nell'interfaccia di amministrazione di SharePoint, nel riquadro di spostamento a sinistra, in **criteri**fare clic su **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="a076c-138">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="a076c-139">Verificare che la condivisione esterna per SharePoint o OneDrive sia impostata su chiunque o su un **utente** **nuovo o esistente**.</span><span class="sxs-lookup"><span data-stu-id="a076c-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="a076c-140">Si noti che l'impostazione di OneDrive non può essere più permissiva dell'impostazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a076c-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="a076c-141">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a076c-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="a076c-142">Impostazioni di collegamento predefinite a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a076c-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="a076c-143">Le impostazioni predefinite per il collegamento di file e cartelle determinano l'opzione di collegamento che verrà visualizzata agli utenti per impostazione predefinita quando condividono un file o una cartella.</span><span class="sxs-lookup"><span data-stu-id="a076c-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="a076c-144">Gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima di condividerlo, se necessario.</span><span class="sxs-lookup"><span data-stu-id="a076c-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="a076c-145">Tenere presente che questa impostazione influisce sui siti di SharePoint nell'organizzazione, nonché OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a076c-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="a076c-146">Scegliere un collegamento tra i tipi seguenti, che vengono quindi selezionati per impostazione predefinita quando gli utenti condividono file e cartelle:</span><span class="sxs-lookup"><span data-stu-id="a076c-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="a076c-147">**Tutti gli utenti con il collegamento** : scegliere questa opzione se si prevede di eseguire molte condivisione di file e cartelle non autenticate.</span><span class="sxs-lookup"><span data-stu-id="a076c-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="a076c-148">Se si desidera consentire collegamenti a *tutti gli utenti* , ma si è preoccupati per la condivisione accidentale non autenticata, prendere in considerazione una delle altre opzioni come impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a076c-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="a076c-149">Questo tipo di collegamento è disponibile solo se è stata abilitata la condivisione di **utenti** .</span><span class="sxs-lookup"><span data-stu-id="a076c-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="a076c-150">**Solo persone nell'organizzazione** : scegliere questa opzione se si prevede che la maggior parte della condivisione di file e cartelle sia con le persone all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a076c-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="a076c-151">**Persone specifiche** : considerare questa opzione se si prevede di eseguire un sacco di condivisione di file e cartelle con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a076c-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="a076c-152">Questo tipo di collegamento è compatibile con gli utenti e richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a076c-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="a076c-154">Per impostare le impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint e OneDrive</span><span class="sxs-lookup"><span data-stu-id="a076c-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="a076c-155">Passare alla pagina condivisione nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a076c-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="a076c-156">In **collegamenti a file e cartelle**selezionare il collegamento di condivisione predefinito che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a076c-156">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="a076c-157">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a076c-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="a076c-158">Per impostare l'autorizzazione per il collegamento di condivisione, in **scegliere l'autorizzazione selezionata per impostazione predefinita per i collegamenti di condivisione.**</span><span class="sxs-lookup"><span data-stu-id="a076c-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="a076c-159">Fare clic su **Visualizza** se non si desidera che gli utenti non autenticati modifichino le modifiche apportate ai file e alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="a076c-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="a076c-160">Selezionare **modifica** se si desidera consentire agli utenti non autenticati di apportare modifiche ai file e alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="a076c-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="a076c-161">Si noti che le due opzioni di premessa precedenti possono essere applicate non solo per gli utenti esterni, ma anche per gli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="a076c-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="a076c-162">L'opzione di autorizzazione scelta è determinata dalla propria discrezione.</span><span class="sxs-lookup"><span data-stu-id="a076c-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="a076c-163">Per impostare le autorizzazioni per i collegamenti che consentono la condivisione con tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="a076c-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="a076c-164">In **questi collegamenti è possibile assegnare le autorizzazioni seguenti:** riquadro secondario,</span><span class="sxs-lookup"><span data-stu-id="a076c-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="a076c-165">Nell'elenco a discesa **file** ,</span><span class="sxs-lookup"><span data-stu-id="a076c-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="a076c-166">Selezionare **Visualizza e modifica** se si desidera consentire agli utenti non autenticati di apportare modifiche ai file.</span><span class="sxs-lookup"><span data-stu-id="a076c-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="a076c-167">Fare clic su **Visualizza** se non si desidera che gli utenti non autenticati apportano modifiche ai file.</span><span class="sxs-lookup"><span data-stu-id="a076c-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="a076c-168">Nell'elenco a discesa **cartelle** ,</span><span class="sxs-lookup"><span data-stu-id="a076c-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="a076c-169">Selezionare **Visualizza, modifica e carica** se si desidera consentire agli utenti non autenticati di apportare modifiche alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="a076c-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="a076c-170">Fare clic su **Visualizza** se non si desidera che gli utenti non autenticati modifichino le cartelle.</span><span class="sxs-lookup"><span data-stu-id="a076c-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="a076c-171">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a076c-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="a076c-172">Se si condividono file e cartelle contenuti in un sito di SharePoint, è necessario controllare anche le impostazioni di condivisione a livello di sito per il sito.</span><span class="sxs-lookup"><span data-stu-id="a076c-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="a076c-174">Per impostare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="a076c-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="a076c-175">Nell'interfaccia di amministrazione di SharePoint, nel riquadro di spostamento a sinistra, espandere **siti** e fare clic su **siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="a076c-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="a076c-176">Selezionare il sito in cui si desidera condividere file e cartelle con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a076c-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="a076c-177">Scorrere a destra sulla riga (in cui è presente il sito selezionato) e fare clic in qualsiasi punto della colonna **condivisione esterna** .</span><span class="sxs-lookup"><span data-stu-id="a076c-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="a076c-178">Dalla pagina che viene visualizzata, fare clic su scheda **criteri** .</span><span class="sxs-lookup"><span data-stu-id="a076c-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="a076c-179">Nel riquadro **condivisione esterna** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a076c-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="a076c-180">Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="a076c-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="a076c-181">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a076c-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="a076c-182">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="a076c-182">Invite users</span></span>

<span data-ttu-id="a076c-183">Le impostazioni di condivisione Guest sono ora configurate; in questo modo gli utenti possono condividere file e cartelle con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a076c-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="a076c-184">Per ulteriori informazioni, vedere [condivisione di file e cartelle di OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) e [condivisione di file o cartelle di SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="a076c-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="a076c-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a076c-185">See also</span></span>

[<span data-ttu-id="a076c-186">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="a076c-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="a076c-187">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="a076c-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="a076c-188">Integrazione di SharePoint e OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="a076c-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
