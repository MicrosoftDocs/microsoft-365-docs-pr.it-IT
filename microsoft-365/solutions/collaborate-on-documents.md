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
ms.openlocfilehash: 1a7591915efa82f1995ce2789e181dc350cd3784
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357783"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="302dd-103">Collaborare con gli utenti guest a un documento</span><span class="sxs-lookup"><span data-stu-id="302dd-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="302dd-104">Se è necessario collaborare con utenti esterni all'organizzazione nei documenti di SharePoint o OneDrive, è possibile inviare un collegamento di condivisione al documento.</span><span class="sxs-lookup"><span data-stu-id="302dd-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="302dd-105">In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare i collegamenti di condivisione per SharePoint e OneDrive per le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302dd-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="302dd-106">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="302dd-106">Video demonstration</span></span>

<span data-ttu-id="302dd-107">In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="302dd-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="302dd-108">Impostazioni delle relazioni organizzative di Azure</span><span class="sxs-lookup"><span data-stu-id="302dd-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="302dd-109">La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni delle relazioni organizzative in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="302dd-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="302dd-110">Se la condivisione Guest è disabilitata o limitata in Azure AD, queste verranno sostituite da tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="302dd-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="302dd-111">Controllare le impostazioni delle relazioni organizzative per garantire che la condivisione con gli ospiti non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="302dd-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="302dd-113">Per impostare le impostazioni delle relazioni organizzative</span><span class="sxs-lookup"><span data-stu-id="302dd-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="302dd-114">Accedere a Microsoft Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="302dd-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="302dd-115">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="302dd-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="302dd-116">Nel riquadro **Panoramica** fare clic su **relazioni organizzative**.</span><span class="sxs-lookup"><span data-stu-id="302dd-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="302dd-117">Nel riquadro **relazioni organizzative** fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="302dd-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="302dd-118">Verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="302dd-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="302dd-119">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="302dd-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="302dd-120">Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** .</span><span class="sxs-lookup"><span data-stu-id="302dd-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="302dd-121">Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="302dd-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="302dd-122">Se si lavora con clienti provenienti da più organizzazioni, è possibile che si desideri limitare la possibilità di accedere ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="302dd-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="302dd-123">Ciò impedirà loro di vedere chi altro è un ospite nella directory.</span><span class="sxs-lookup"><span data-stu-id="302dd-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="302dd-124">Per eseguire questa operazione, in **restrizioni di accesso degli utenti Guest**, selezionare **Guest gli utenti hanno accesso limitato alle proprietà e l'appartenenza delle impostazioni degli oggetti directory** o **l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti directory**.</span><span class="sxs-lookup"><span data-stu-id="302dd-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="302dd-125">Impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="302dd-125">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="302dd-126">Affinché gli utenti esterni all'organizzazione abbiano accesso a un documento in SharePoint o OneDrive, le impostazioni di condivisione a livello di organizzazione di SharePoint e OneDrive devono consentire la condivisione con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302dd-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="302dd-127">Le impostazioni a livello di organizzazione per SharePoint determinano le impostazioni disponibili per i singoli siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="302dd-127">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="302dd-128">Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302dd-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="302dd-129">L'impostazione a livello di organizzazione per OneDrive determina il livello di condivisione disponibile nelle raccolte OneDrive degli utenti.</span><span class="sxs-lookup"><span data-stu-id="302dd-129">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="302dd-130">Per SharePoint e OneDrive, se si desidera consentire la condivisione di file e cartelle non autenticata, scegliere **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="302dd-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="302dd-131">Se si desidera garantire che gli utenti esterni all'organizzazione debbano eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="302dd-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="302dd-132">*Tutti* i collegamenti sono il modo più semplice per condividere: gli utenti esterni all'organizzazione possono aprire il collegamento senza l'autenticazione e sono liberi di passarlo ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="302dd-132">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="302dd-133">Per SharePoint, scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302dd-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="302dd-135">Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="302dd-135">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="302dd-136">Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento a sinistra, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="302dd-136">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="302dd-137">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="302dd-137">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="302dd-138">Verificare che la condivisione esterna per SharePoint o OneDrive sia impostata su chiunque o su un **utente** **nuovo o esistente**.</span><span class="sxs-lookup"><span data-stu-id="302dd-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="302dd-139">Si noti che l'impostazione di OneDrive non può essere più permissiva dell'impostazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="302dd-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="302dd-140">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="302dd-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="302dd-141">Impostazioni di collegamento predefinite a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="302dd-141">SharePoint organization level default link settings</span></span>

<span data-ttu-id="302dd-142">Le impostazioni predefinite per il collegamento di file e cartelle determinano l'opzione di collegamento visualizzata all'utente per impostazione predefinita quando condividono un file o una cartella.</span><span class="sxs-lookup"><span data-stu-id="302dd-142">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="302dd-143">Gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima della condivisione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="302dd-143">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="302dd-144">Tenere presente che questa impostazione influisce sui siti di SharePoint nell'organizzazione, nonché OneDrive.</span><span class="sxs-lookup"><span data-stu-id="302dd-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="302dd-145">Scegliere il tipo di collegamento selezionato per impostazione predefinita quando gli utenti condividono file e cartelle:</span><span class="sxs-lookup"><span data-stu-id="302dd-145">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="302dd-146">**Tutti gli utenti con il collegamento** : scegliere questa opzione se si prevede di eseguire molte condivisione di file e cartelle non autenticate.</span><span class="sxs-lookup"><span data-stu-id="302dd-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="302dd-147">Se si desidera consentire collegamenti a *tutti gli utenti* , ma si è preoccupati per la condivisione accidentale non autenticata, prendere in considerazione una delle altre opzioni come impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="302dd-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="302dd-148">Questo tipo di collegamento è disponibile solo se è stata abilitata la condivisione di **utenti** .</span><span class="sxs-lookup"><span data-stu-id="302dd-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="302dd-149">**Solo persone nell'organizzazione** : scegliere questa opzione se si prevede che la maggior parte della condivisione di file e cartelle sia con le persone all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302dd-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="302dd-150">**Persone specifiche** : considerare questa opzione se si prevede di eseguire un sacco di condivisione di file e cartelle con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="302dd-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="302dd-151">Questo tipo di collegamento è compatibile con gli utenti e richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="302dd-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="302dd-153">Per impostare le impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint e OneDrive</span><span class="sxs-lookup"><span data-stu-id="302dd-153">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="302dd-154">Passare alla pagina condivisione nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="302dd-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="302dd-155">In **collegamenti a file e cartelle**selezionare il collegamento di condivisione predefinito che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="302dd-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="302dd-156">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="302dd-156">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="302dd-157">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="302dd-157">SharePoint site level sharing settings</span></span>

<span data-ttu-id="302dd-158">Se si condividono file e cartelle contenuti in un sito di SharePoint, è necessario controllare anche le impostazioni di condivisione a livello di sito per il sito.</span><span class="sxs-lookup"><span data-stu-id="302dd-158">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="302dd-160">Per impostare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="302dd-160">To set site-level sharing settings</span></span>
1. <span data-ttu-id="302dd-161">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="302dd-161">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="302dd-162">Selezionare il sito appena creato.</span><span class="sxs-lookup"><span data-stu-id="302dd-162">Select the site that you just created.</span></span>
3. <span data-ttu-id="302dd-163">Sulla barra multifunzione fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="302dd-163">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="302dd-164">Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="302dd-164">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="302dd-165">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="302dd-165">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="302dd-166">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="302dd-166">Invite users</span></span>

<span data-ttu-id="302dd-167">Le impostazioni di condivisione Guest sono ora configurate, quindi gli utenti possono ora condividere file e cartelle con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302dd-167">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="302dd-168">Per ulteriori informazioni, vedere [condivisione di file e cartelle di OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) e [condivisione di file o cartelle di SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="302dd-168">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="302dd-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="302dd-169">See Also</span></span>

[<span data-ttu-id="302dd-170">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="302dd-170">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="302dd-171">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="302dd-171">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="302dd-172">Integrazione di SharePoint e OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="302dd-172">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)