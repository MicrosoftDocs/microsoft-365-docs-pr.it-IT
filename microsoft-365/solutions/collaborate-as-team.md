---
title: Collaborare con gli utenti guest in un team
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
description: Informazioni sui passaggi di configurazione di Microsoft 365 necessari per configurare un team per l'attività, la conversazione e la documentazione per la collaborazione con i clienti del team.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780545"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="5f50c-103">Collaborare con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="5f50c-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="5f50c-104">Se è necessario collaborare con gli utenti tra documenti, attività e conversazioni, è consigliabile utilizzare Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="5f50c-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="5f50c-105">Teams offre tutte le funzionalità di collaborazione disponibili in Office e SharePoint con chat persistente e un set di strumenti di collaborazione personalizzabile ed estensibile in un'esperienza utente unificata.</span><span class="sxs-lookup"><span data-stu-id="5f50c-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="5f50c-106">In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare un team per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5f50c-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="5f50c-107">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="5f50c-107">Video demonstration</span></span>

<span data-ttu-id="5f50c-108">In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="5f50c-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="5f50c-109">Impostazioni di collaborazione esterna di Azure</span><span class="sxs-lookup"><span data-stu-id="5f50c-109">Azure External collaboration settings</span></span>

<span data-ttu-id="5f50c-110">La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni di collaborazione esterna B2B in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="5f50c-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="5f50c-111">Se la condivisione Guest è disabilitata o limitata in Azure AD, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f50c-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="5f50c-112">Controllare le impostazioni di collaborazione esterna B2B per garantire che la condivisione con gli utenti non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="5f50c-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="5f50c-114">Per impostare le impostazioni di collaborazione esterna</span><span class="sxs-lookup"><span data-stu-id="5f50c-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="5f50c-115">Accedere a Azure Active Directory all'indirizzo [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="5f50c-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="5f50c-116">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5f50c-117">Fare clic su **identità esterne**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-117">Click **External identities**.</span></span>
4. <span data-ttu-id="5f50c-118">Nella schermata **inizia** , nel riquadro di spostamento a sinistra, fare clic su **impostazioni di collaborazione esterna**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="5f50c-119">Verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="5f50c-120">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="5f50c-121">Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** .</span><span class="sxs-lookup"><span data-stu-id="5f50c-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="5f50c-122">Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="5f50c-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="5f50c-123">Se si lavora con clienti provenienti da più organizzazioni, è possibile che si desideri limitare la possibilità di accedere ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="5f50c-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="5f50c-124">Ciò impedirà loro di vedere chi altro è un ospite nella directory.</span><span class="sxs-lookup"><span data-stu-id="5f50c-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="5f50c-125">Per eseguire questa operazione, in **restrizioni di accesso degli utenti Guest**, selezionare **Guest gli utenti hanno accesso limitato alle proprietà e l'appartenenza delle impostazioni degli oggetti directory** o **l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti directory**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="5f50c-126">Impostazioni di accesso Guest Teams</span><span class="sxs-lookup"><span data-stu-id="5f50c-126">Teams guest access settings</span></span>

<span data-ttu-id="5f50c-127">I team dispongono di un'opzione Master di attivazione/disattivazione dell'accesso guest e di una serie di impostazioni disponibili per controllare gli utenti che possono eseguire in un team.</span><span class="sxs-lookup"><span data-stu-id="5f50c-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="5f50c-128">L'opzione master **consente all'accesso guest nei team** di essere **attiva** per l'accesso guest per il lavoro in teams.</span><span class="sxs-lookup"><span data-stu-id="5f50c-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="5f50c-129">Verificare che l'accesso Guest sia abilitato nei team e apportare eventuali adeguamenti alle impostazioni guest in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="5f50c-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="5f50c-130">Tenere presente che queste impostazioni influiscono su tutti i team.</span><span class="sxs-lookup"><span data-stu-id="5f50c-130">Keep in mind that these settings affect all teams.</span></span>

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="5f50c-132">Per configurare le impostazioni di accesso guest di Teams</span><span class="sxs-lookup"><span data-stu-id="5f50c-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="5f50c-133">Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5f50c-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="5f50c-134">Nel riquadro di spostamento a sinistra, fare clic su **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="5f50c-135">In **Interfacce di amministrazione** fare clic su **Teams**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="5f50c-136">Nell'interfaccia di amministrazione dei team, nel riquadro di spostamento a sinistra, espandere **impostazioni a livello di organizzazione** e fare clic su **accesso Guest**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="5f50c-137">Assicurarsi che l'opzione **Consenti accesso ospite in Teams** sia \*\*\*\* abilitata.</span><span class="sxs-lookup"><span data-stu-id="5f50c-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="5f50c-138">Apportare le modifiche desiderate alle impostazioni guest aggiuntive e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="5f50c-139">Dopo aver abilitato l'accesso Guest ai team, è possibile controllare l'accesso Guest ai singoli team e ai siti di SharePoint associati utilizzando le etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="5f50c-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="5f50c-140">Per altre informazioni, vedere [Usare le etichette di riservatezza per proteggere i contenuti in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="5f50c-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="5f50c-141">Dopo averla attivata, potrebbero essere necessarie fino a ventiquattro ore per rendere attive le impostazioni Guest del team.</span><span class="sxs-lookup"><span data-stu-id="5f50c-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="5f50c-142">Microsoft 365 groups Guest Settings</span><span class="sxs-lookup"><span data-stu-id="5f50c-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="5f50c-143">Teams utilizza i gruppi di Microsoft 365 per l'appartenenza al team.</span><span class="sxs-lookup"><span data-stu-id="5f50c-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="5f50c-144">È necessario che le impostazioni Guest dei gruppi Microsoft 365 siano attivate in modo che l'accesso guest nei team funzioni.</span><span class="sxs-lookup"><span data-stu-id="5f50c-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="5f50c-146">Per impostare Microsoft 365 groups Guest Settings</span><span class="sxs-lookup"><span data-stu-id="5f50c-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="5f50c-147">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, espandere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="5f50c-148">Fare clic su **Impostazioni organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="5f50c-149">Nell'elenco, fare clic su **gruppi Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="5f50c-150">Assicurarsi che i **proprietari di Let Group aggiungano le persone all'esterno dell'organizzazione ai gruppi di Microsoft 365 come ospiti** e che i **membri del gruppo di accesso al contenuto del** gruppo siano entrambi controllati.</span><span class="sxs-lookup"><span data-stu-id="5f50c-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="5f50c-151">Se sono state apportate modifiche, fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="5f50c-152">Impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f50c-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="5f50c-153">I contenuti dei team, ad esempio file, cartelle ed elenchi, sono tutti archiviati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5f50c-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="5f50c-154">Per consentire agli utenti di accedere a questi elementi nei team, le impostazioni di condivisione a livello dell'organizzazione di SharePoint devono essere consentite per la condivisione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5f50c-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="5f50c-155">Le impostazioni a livello di organizzazione determinano le impostazioni disponibili per i singoli siti, inclusi i siti associati ai team.</span><span class="sxs-lookup"><span data-stu-id="5f50c-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="5f50c-156">Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f50c-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="5f50c-157">Se si desidera consentire la condivisione di file e cartelle con persone non autenticate, scegliere **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="5f50c-158">Se si desidera garantire che tutti gli utenti siano in grado di eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="5f50c-159">Scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f50c-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="5f50c-161">Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f50c-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="5f50c-162">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="5f50c-163">Nell'interfaccia di amministrazione di SharePoint, nel riquadro di spostamento a sinistra, espandere **criteri** e quindi fare clic su **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="5f50c-164">Assicurarsi che la condivisione esterna per SharePoint sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="5f50c-165">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="5f50c-166">Impostazioni di collegamento predefinite a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f50c-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="5f50c-167">Le impostazioni predefinite per il collegamento di file e cartelle determinano l'opzione di collegamento che verrà visualizzata agli utenti per impostazione predefinita quando condividono un file o una cartella.</span><span class="sxs-lookup"><span data-stu-id="5f50c-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="5f50c-168">Gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima di condividerlo, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5f50c-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="5f50c-169">Tenere presente che questa impostazione ha effetto su tutti i team e i siti di SharePoint dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f50c-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="5f50c-170">Scegliere uno dei seguenti tipi di collegamento che verranno selezionati per impostazione predefinita quando gli utenti condividono file e cartelle:</span><span class="sxs-lookup"><span data-stu-id="5f50c-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="5f50c-171">**Tutti gli utenti con il collegamento** : scegliere questa opzione se si prevede di eseguire la condivisione di file e cartelle in modo molto non autenticato.</span><span class="sxs-lookup"><span data-stu-id="5f50c-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="5f50c-172">Se si desidera consentire collegamenti a *tutti gli utenti* , ma si è preoccupati per la condivisione accidentale non autenticata, prendere in considerazione una delle altre opzioni come impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5f50c-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="5f50c-173">Questo tipo di collegamento è disponibile solo se è stata abilitata la condivisione di **utenti** .</span><span class="sxs-lookup"><span data-stu-id="5f50c-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="5f50c-174">**Solo persone nell'organizzazione** : scegliere questa opzione se si prevede che la maggior parte della condivisione di file e cartelle sia con le persone all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f50c-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="5f50c-175">**Persone specifiche** : considerare questa opzione se si prevede di eseguire un sacco di condivisione di file e cartelle con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5f50c-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="5f50c-176">Questo tipo di collegamento è compatibile con gli utenti e richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5f50c-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="5f50c-178">Per impostare le impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f50c-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="5f50c-179">Passare alla pagina condivisione nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5f50c-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="5f50c-180">In **collegamenti a file e cartelle** selezionare il collegamento di condivisione predefinito che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5f50c-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="5f50c-181">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="5f50c-182">Creare un team</span><span class="sxs-lookup"><span data-stu-id="5f50c-182">Create a team</span></span>

<span data-ttu-id="5f50c-183">Il passaggio successivo consiste nel creare il team che si intende utilizzare per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5f50c-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="5f50c-184">Per creare un team</span><span class="sxs-lookup"><span data-stu-id="5f50c-184">To create a team</span></span>
1. <span data-ttu-id="5f50c-185">In teams fare clic su **join oppure creare un team** nella parte inferiore del riquadro sinistro nella scheda **Teams** .</span><span class="sxs-lookup"><span data-stu-id="5f50c-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="5f50c-186">Fare clic su **Crea team**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="5f50c-187">Fare clic su **Crea un team da zero**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="5f50c-188">Scegliere **privato** o **pubblico**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="5f50c-189">Digitare un nome e una descrizione per il team, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="5f50c-190">Fare clic su **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-190">Click **Skip**.</span></span>

<span data-ttu-id="5f50c-191">Gli utenti verranno invitati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="5f50c-191">We'll invite users later.</span></span> <span data-ttu-id="5f50c-192">Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito di SharePoint associato al team.</span><span class="sxs-lookup"><span data-stu-id="5f50c-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="5f50c-193">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f50c-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="5f50c-194">Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il team.</span><span class="sxs-lookup"><span data-stu-id="5f50c-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="5f50c-195">Ad esempio, se si impostano le impostazioni a livello di organizzazione per tutti gli **utenti**, ma si desidera che tutti gli ospiti eseguano l'autenticazione per questo team, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su **Guest nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="5f50c-197">Per impostare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="5f50c-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="5f50c-198">Nell'interfaccia di amministrazione di SharePoint, nel riquadro di spostamento a sinistra, espandere **siti** e fare clic su **siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="5f50c-199">Selezionare il sito del team appena creato.</span><span class="sxs-lookup"><span data-stu-id="5f50c-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="5f50c-200">Fare clic su... e scegli **condivisione**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="5f50c-201">Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="5f50c-202">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="5f50c-203">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="5f50c-203">Invite users</span></span>

<span data-ttu-id="5f50c-204">Le impostazioni di condivisione Guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e ospiti al team.</span><span class="sxs-lookup"><span data-stu-id="5f50c-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="5f50c-205">Per invitare gli utenti interni a un team</span><span class="sxs-lookup"><span data-stu-id="5f50c-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="5f50c-206">Nel team, fare clic su **altre opzioni** ( **\*\*\*** ), quindi fare clic su **Aggiungi membro**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="5f50c-207">Digitare il nome della persona che si desidera invitare.</span><span class="sxs-lookup"><span data-stu-id="5f50c-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="5f50c-208">Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="5f50c-209">Per invitare gli ospiti a un team</span><span class="sxs-lookup"><span data-stu-id="5f50c-209">To invite guests to a team</span></span>
1. <span data-ttu-id="5f50c-210">Nel team, fare clic su **altre opzioni** ( **\*\*\*** ), quindi fare clic su **Aggiungi membro**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="5f50c-211">Digitare l'indirizzo di posta elettronica dell'ospite che si desidera invitare.</span><span class="sxs-lookup"><span data-stu-id="5f50c-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="5f50c-212">Fare clic su **modifica informazioni Guest**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="5f50c-213">Digitare il nome completo dell'ospite e fare clic sul segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="5f50c-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="5f50c-214">Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="5f50c-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f50c-215">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f50c-215">See also</span></span>

[<span data-ttu-id="5f50c-216">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="5f50c-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="5f50c-217">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="5f50c-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="5f50c-218">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="5f50c-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="5f50c-219">[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="5f50c-219">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

[<span data-ttu-id="5f50c-220">Integrazione di SharePoint e OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="5f50c-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="5f50c-221">Le opzioni di condivisione sono ingrigiate quando si condivide da SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="5f50c-221">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
