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
description: Informazioni sui passaggi di configurazione di Microsoft 365 necessari per configurare un team per la collaborazione su attività, conversazioni e documentazione con gli utenti guest in Teams.
ms.openlocfilehash: 66c5692dd8cd233d8b3639f8ce0755ce51b60c0a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233075"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="8d10e-103">Collaborare con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="8d10e-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="8d10e-104">Se è necessario collaborare con gli utenti guest tra documenti, attività e conversazioni, è consigliabile usare Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8d10e-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="8d10e-105">Teams offre tutte le funzionalità di collaborazione disponibili in Office e SharePoint con chat persistente e un set personalizzabile ed estendibile di strumenti di collaborazione in un'esperienza utente unificata.</span><span class="sxs-lookup"><span data-stu-id="8d10e-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="8d10e-106">In questo articolo verranno descritti i passaggi di configurazione di Microsoft 365 necessari per configurare un team per la collaborazione con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="8d10e-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="8d10e-107">Dopo aver configurato l'accesso guest, è possibile invitare utenti guest a team seguendo la procedura descritta in [Aggiungere guest a un team in Teams.](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="8d10e-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="8d10e-108">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="8d10e-108">Video demonstration</span></span>

<span data-ttu-id="8d10e-109">In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="8d10e-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="8d10e-110">Impostazioni di collaborazione esterna di Azure</span><span class="sxs-lookup"><span data-stu-id="8d10e-110">Azure External collaboration settings</span></span>

<span data-ttu-id="8d10e-111">La condivisione in Microsoft 365 è regolata al livello più alto dalle impostazioni di collaborazione esterna [B2B in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="8d10e-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="8d10e-112">Se la condivisione guest è disabilitata o limitata in Azure AD, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d10e-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="8d10e-113">Controllare le impostazioni di collaborazione esterna B2B per assicurarsi che la condivisione con gli utenti guest non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="8d10e-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="8d10e-115">Per impostare le impostazioni di collaborazione esterna</span><span class="sxs-lookup"><span data-stu-id="8d10e-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="8d10e-116">Accedere ad Azure Active Directory all'indirizzo [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="8d10e-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="8d10e-117">Nel riquadro di spostamento sinistro fare clic su **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="8d10e-118">Fare **clic su Identità esterne.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-118">Click **External identities**.</span></span>
4. <span data-ttu-id="8d10e-119">Nel riquadro **di spostamento sinistro** della schermata Introduzione fare clic su Impostazioni collaborazione **esterna.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="8d10e-120">Verificare che **gli amministratori e gli utenti** nel  ruolo di mittente dell'invito guest possano invitare e che i membri possano invitare siano entrambi impostati su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="8d10e-121">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8d10e-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="8d10e-122">Prendere nota delle impostazioni nella **sezione Restrizioni di** collaborazione.</span><span class="sxs-lookup"><span data-stu-id="8d10e-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="8d10e-123">Assicurarsi che i domini dei guest con cui si vuole collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="8d10e-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="8d10e-124">Se si lavora con utenti guest di più organizzazioni, è possibile limitare la possibilità di accedere ai dati della directory.</span><span class="sxs-lookup"><span data-stu-id="8d10e-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="8d10e-125">Ciò impedirà loro di vedere chi altro è un guest nella directory.</span><span class="sxs-lookup"><span data-stu-id="8d10e-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="8d10e-126">A tale scopo, in Restrizioni di accesso degli utenti **guest,** selezionare Gli utenti guest hanno accesso limitato alle proprietà e l'appartenenza alle impostazioni degli oggetti **directory** o l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti **directory.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="8d10e-127">Impostazioni di accesso guest di Teams</span><span class="sxs-lookup"><span data-stu-id="8d10e-127">Teams guest access settings</span></span>

<span data-ttu-id="8d10e-128">Teams dispone di un interruttore master on/off per l'accesso guest e di un'ampia gamma di impostazioni disponibili per controllare le operazioni che gli utenti guest possono eseguire in un team.</span><span class="sxs-lookup"><span data-stu-id="8d10e-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="8d10e-129">L'opzione master Consenti **l'accesso guest in Teams** deve essere **attivata** perché l'accesso guest funzioni in Teams.</span><span class="sxs-lookup"><span data-stu-id="8d10e-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="8d10e-130">Verificare che l'accesso guest sia abilitato in Teams e apportare eventuali modifiche alle impostazioni guest in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="8d10e-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="8d10e-131">Tenere presente che queste impostazioni influiscono su tutti i team.</span><span class="sxs-lookup"><span data-stu-id="8d10e-131">Keep in mind that these settings affect all teams.</span></span>

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="8d10e-133">Per configurare le impostazioni di accesso guest di Teams</span><span class="sxs-lookup"><span data-stu-id="8d10e-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="8d10e-134">Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8d10e-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="8d10e-135">Nel riquadro di spostamento sinistro fare clic su **Mostra tutto.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="8d10e-136">In **Interfacce di amministrazione** fare clic su **Teams**.</span><span class="sxs-lookup"><span data-stu-id="8d10e-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="8d10e-137">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello** di organizzazione e fare clic su Accesso **guest.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="8d10e-138">Assicurarsi che l'opzione **Consenti accesso ospite in Teams** sia \*\*\*\* abilitata.</span><span class="sxs-lookup"><span data-stu-id="8d10e-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="8d10e-139">Apportare le modifiche desiderate alle impostazioni guest aggiuntive e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8d10e-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="8d10e-140">Una volta attivato l'accesso guest di Teams, è possibile controllare facoltativamente l'accesso guest ai singoli team e ai siti di SharePoint associati utilizzando le etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="8d10e-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="8d10e-141">Per altre informazioni, vedere [Usare le etichette di riservatezza per proteggere i contenuti in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="8d10e-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="8d10e-142">Potrebbero essere necessario fino a 24 ore prima che le impostazioni guest di Teams diventino attive dopo l'attivazione.</span><span class="sxs-lookup"><span data-stu-id="8d10e-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="8d10e-143">Impostazioni guest dei gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d10e-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="8d10e-144">Teams usa i gruppi di Microsoft 365 per l'appartenenza al team.</span><span class="sxs-lookup"><span data-stu-id="8d10e-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="8d10e-145">Le impostazioni guest dei gruppi di Microsoft 365 devono essere attivate per consentire il funzionamento dell'accesso guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="8d10e-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="8d10e-147">Per configurare le impostazioni guest dei gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d10e-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="8d10e-148">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 espandere **Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="8d10e-149">Fare **clic su Impostazioni organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="8d10e-150">Nell'elenco fare clic su **Gruppi di Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="8d10e-151">Verificare che le caselle di controllo Consenti ai proprietari del gruppo di aggiungere persone esterne all'organizzazione ai gruppi di **Microsoft 365** come guest e che le caselle di controllo Consenti ai membri del gruppo **guest** di accedere al contenuto del gruppo siano entrambe selezionate.</span><span class="sxs-lookup"><span data-stu-id="8d10e-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="8d10e-152">Se sono state apportate modifiche, fare clic **su Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="8d10e-153">Impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d10e-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="8d10e-154">I contenuti di Teams, ad esempio file, cartelle ed elenchi, vengono tutti archiviati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8d10e-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="8d10e-155">Per consentire agli utenti guest di accedere a questi elementi in Teams, le impostazioni di condivisione a livello di organizzazione di SharePoint devono consentire la condivisione con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="8d10e-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="8d10e-156">Le impostazioni a livello di organizzazione determinano le impostazioni disponibili per i singoli siti, inclusi i siti associati ai team.</span><span class="sxs-lookup"><span data-stu-id="8d10e-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="8d10e-157">Le impostazioni del sito non possono essere più permissive delle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d10e-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="8d10e-158">Se si desidera consentire la condivisione di file e cartelle con utenti non autenticati, scegliere **Chiunque.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="8d10e-159">Se si desidera assicurarsi che tutti gli utenti guest devono eseguire l'autenticazione, scegliere Utenti guest **nuovi ed esistenti.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="8d10e-160">Scegliere l'impostazione più permissiva che sarà necessaria a qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d10e-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="8d10e-162">Per configurare le impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d10e-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="8d10e-163">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, in **Interfaccia di amministrazione,** fare clic su **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="8d10e-164">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di SharePoint espandere **Criteri** e quindi fare clic su **Condivisione.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="8d10e-165">Verificare che la condivisione esterna per SharePoint sia impostata su **Chiunque** o Utenti guest nuovi **ed esistenti.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="8d10e-166">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8d10e-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="8d10e-167">Impostazioni di collegamento predefinite a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d10e-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="8d10e-168">Le impostazioni predefinite dei collegamenti a file e cartelle determinano l'opzione di collegamento che verrà visualizzata agli utenti per impostazione predefinita quando condividono un file o una cartella.</span><span class="sxs-lookup"><span data-stu-id="8d10e-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="8d10e-169">Gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima della condivisione, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="8d10e-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="8d10e-170">Tenere presente che questa impostazione influisce su tutti i team e i siti di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d10e-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="8d10e-171">Scegliere uno dei tipi di collegamento seguenti che verranno selezionati per impostazione predefinita quando gli utenti condividono file e cartelle:</span><span class="sxs-lookup"><span data-stu-id="8d10e-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="8d10e-172">**Chiunque abbia il collegamento:** scegliere questa opzione se si prevede di eseguire una grande condivisione non autenticata di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="8d10e-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="8d10e-173">Se si desidera consentire collegamenti *chiunque* ma si è preoccupati per la condivisione accidentale non autenticata, considerare una delle altre opzioni come predefinita.</span><span class="sxs-lookup"><span data-stu-id="8d10e-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="8d10e-174">Questo tipo di collegamento è disponibile solo se è stata abilitata la **condivisione chiunque.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="8d10e-175">**Solo gli utenti dell'organizzazione:** scegliere questa opzione se si prevede che la maggior parte della condivisione di file e cartelle sia con utenti interni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d10e-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="8d10e-176">**Persone specifiche:** considerare questa opzione se si prevede di eseguire molte attività di condivisione di file e cartelle con utenti guest.</span><span class="sxs-lookup"><span data-stu-id="8d10e-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="8d10e-177">Questo tipo di collegamento funziona con gli utenti guest e richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8d10e-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="8d10e-179">Per impostare le impostazioni di collegamento predefinite a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d10e-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="8d10e-180">Passare alla pagina Condivisione nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8d10e-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="8d10e-181">In **Collegamenti a file e cartelle** selezionare il collegamento di condivisione predefinito che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8d10e-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="8d10e-182">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8d10e-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="8d10e-183">Creare un team</span><span class="sxs-lookup"><span data-stu-id="8d10e-183">Create a team</span></span>

<span data-ttu-id="8d10e-184">Il passaggio successivo consiste nel creare il team che si prevede di usare per la collaborazione con gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="8d10e-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="8d10e-185">Per creare un team</span><span class="sxs-lookup"><span data-stu-id="8d10e-185">To create a team</span></span>
1. <span data-ttu-id="8d10e-186">In Teams, nella scheda **Teams,** fare clic su **Partecipa o crea un team** nella parte inferiore del riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="8d10e-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="8d10e-187">Fare **clic su Crea team.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="8d10e-188">Fare **clic su Crea un team da zero.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="8d10e-189">Scegliere **Privato** o **Pubblico.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="8d10e-190">Digitare un nome e una descrizione per il team e quindi fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="8d10e-191">Fare **clic su Ignora.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-191">Click **Skip**.</span></span>

<span data-ttu-id="8d10e-192">Inviteremo gli utenti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="8d10e-192">We'll invite users later.</span></span> <span data-ttu-id="8d10e-193">Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito di SharePoint associato al team.</span><span class="sxs-lookup"><span data-stu-id="8d10e-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="8d10e-194">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d10e-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="8d10e-195">Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il team.</span><span class="sxs-lookup"><span data-stu-id="8d10e-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="8d10e-196">Ad esempio, se si impostano le impostazioni a livello di organizzazione su **Chiunque**, ma si desidera che tutti gli utenti guest eseercitino l'autenticazione per questo team, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su Utenti guest nuovi ed **esistenti.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="8d10e-198">Per configurare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="8d10e-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="8d10e-199">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di SharePoint espandere **Siti** e fare clic su **Siti attivi.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="8d10e-200">Selezionare il sito del team appena creato.</span><span class="sxs-lookup"><span data-stu-id="8d10e-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="8d10e-201">Fare clic su ... e scegliere **Condivisione.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="8d10e-202">Verificare che la condivisione sia impostata **su Chiunque o** Utenti guest nuovi ed **esistenti.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="8d10e-203">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8d10e-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="8d10e-204">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="8d10e-204">Invite users</span></span>

<span data-ttu-id="8d10e-205">Le impostazioni di condivisione guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e guest al team.</span><span class="sxs-lookup"><span data-stu-id="8d10e-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="8d10e-206">Per invitare utenti interni a un team</span><span class="sxs-lookup"><span data-stu-id="8d10e-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="8d10e-207">Nel team fare clic su **Altre opzioni** ( ) e quindi su **\*\*\*** Aggiungi **membro.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="8d10e-208">Digitare il nome della persona che si desidera invitare.</span><span class="sxs-lookup"><span data-stu-id="8d10e-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="8d10e-209">Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8d10e-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="8d10e-210">Per invitare utenti guest a un team</span><span class="sxs-lookup"><span data-stu-id="8d10e-210">To invite guests to a team</span></span>
1. <span data-ttu-id="8d10e-211">Nel team fare clic su **Altre opzioni** ( ) e quindi su **\*\*\*** Aggiungi **membro.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="8d10e-212">Digitare l'indirizzo di posta elettronica del guest che si desidera invitare.</span><span class="sxs-lookup"><span data-stu-id="8d10e-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="8d10e-213">Fare **clic su Modifica informazioni guest.**</span><span class="sxs-lookup"><span data-stu-id="8d10e-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="8d10e-214">Digitare il nome completo del guest e fare clic sul segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="8d10e-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="8d10e-215">Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8d10e-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d10e-216">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d10e-216">See also</span></span>

[<span data-ttu-id="8d10e-217">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="8d10e-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="8d10e-218">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="8d10e-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="8d10e-219">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="8d10e-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="8d10e-220">[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="8d10e-220">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>

[<span data-ttu-id="8d10e-221">Integrazione di SharePoint e OneDrive con Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="8d10e-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="8d10e-222">Le opzioni di condivisione sono disattivate durante la condivisione da SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="8d10e-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
