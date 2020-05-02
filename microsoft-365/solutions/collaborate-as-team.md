---
title: Collaborare con gli utenti guest in un team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
ms.custom:
- M365solutions
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni su come collaborare con gli utenti in teams.
ms.openlocfilehash: 7d840628ce6d987a907e8be2c8a3c3c5125f7d33
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002193"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="4ff7a-103">Collaborare con gli utenti guest in un team</span><span class="sxs-lookup"><span data-stu-id="4ff7a-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="4ff7a-104">Se è necessario collaborare con gli utenti tra documenti, attività e conversazioni, è consigliabile utilizzare Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="4ff7a-105">Teams offre tutte le funzionalità di collaborazione disponibili in Office e SharePoint con chat persistente e un set di strumenti di collaborazione personalizzabile ed estensibile in un'esperienza utente unificata.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="4ff7a-106">In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare un team per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="4ff7a-107">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="4ff7a-107">Video demonstration</span></span>

<span data-ttu-id="4ff7a-108">In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="4ff7a-109">Impostazioni delle relazioni organizzative di Azure</span><span class="sxs-lookup"><span data-stu-id="4ff7a-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="4ff7a-110">La condivisione in Microsoft 365 è regolata al livello più alto dalle impostazioni delle relazioni organizzative in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="4ff7a-111">Se la condivisione Guest è disabilitata o limitata in Azure AD, queste verranno sostituite da tutte le impostazioni di condivisione configurate in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="4ff7a-112">Controllare le impostazioni delle relazioni organizzative per garantire che la condivisione con gli ospiti non sia bloccata.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="4ff7a-114">Per impostare le impostazioni delle relazioni organizzative</span><span class="sxs-lookup"><span data-stu-id="4ff7a-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="4ff7a-115">Accedere a Microsoft Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="4ff7a-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="4ff7a-116">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="4ff7a-117">Nel riquadro **Panoramica** fare clic su **relazioni organizzative**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="4ff7a-118">Nel riquadro **relazioni organizzative** fare clic su **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="4ff7a-119">Verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="4ff7a-120">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="4ff7a-121">Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** .</span><span class="sxs-lookup"><span data-stu-id="4ff7a-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="4ff7a-122">Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="4ff7a-123">Impostazioni di accesso Guest Teams</span><span class="sxs-lookup"><span data-stu-id="4ff7a-123">Teams guest access settings</span></span>

<span data-ttu-id="4ff7a-124">I team dispongono di un'opzione Master di attivazione/disattivazione dell'accesso guest e di una serie di impostazioni disponibili per controllare gli utenti che possono eseguire in un team.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-124">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="4ff7a-125">L'opzione master **consente all'accesso guest nei team** di essere **attiva** per l'accesso guest per il lavoro in teams.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-125">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="4ff7a-126">Verificare che l'accesso Guest sia abilitato nei team e apportare eventuali adeguamenti alle impostazioni guest in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-126">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="4ff7a-127">Tenere presente che queste impostazioni influiscono su tutti i team.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-127">Keep in mind that these settings affect all teams.</span></span>

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="4ff7a-129">Per impostare le impostazioni di accesso guest di Teams</span><span class="sxs-lookup"><span data-stu-id="4ff7a-129">To set Teams guest access settings</span></span>

1. <span data-ttu-id="4ff7a-130">Accedere all'interfaccia di amministrazione di Microsoft 365 all' [https://admin.microsoft.com](https://admin.microsoft.com)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-130">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="4ff7a-131">Nella barra di spostamento a sinistra, fare clic su **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-131">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="4ff7a-132">In interfaccia di **Amministrazione**fare clic su **Team**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-132">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="4ff7a-133">Nell'interfaccia di amministrazione di teams, nella barra di spostamento a sinistra, espandere **impostazioni a livello di organizzazione** e fare clic su **accesso Guest**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-133">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="4ff7a-134">Verificare che **Consenti accesso guest in teams** sia impostato **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-134">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="4ff7a-135">Apportare le modifiche desiderate alle impostazioni aggiuntive per gli ospiti e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-135">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="4ff7a-136">Dopo l'attivazione, potrebbero essere necessarie fino a ventiquattro ore affinché l'impostazione Guest teams diventi attiva.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-136">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="4ff7a-137">Microsoft 365 groups Guest Settings</span><span class="sxs-lookup"><span data-stu-id="4ff7a-137">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="4ff7a-138">Teams utilizza i gruppi di Microsoft 365 per l'appartenenza al team.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-138">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="4ff7a-139">È necessario che le impostazioni Guest dei gruppi Microsoft 365 siano attivate in modo che l'accesso guest nei team funzioni.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-139">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="4ff7a-141">Per impostare Microsoft 365 groups Guest Settings</span><span class="sxs-lookup"><span data-stu-id="4ff7a-141">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="4ff7a-142">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, espandere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-142">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="4ff7a-143">Fare clic su **servizi & componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-143">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="4ff7a-144">Nell'elenco, fare clic su **gruppi Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-144">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="4ff7a-145">Verificare che i membri del gruppo Consenti al di **fuori dell'organizzazione accedano al contenuto del gruppo** e che i proprietari del **gruppo aggiungano persone all'esterno dell'organizzazione ai gruppi di caselle di** controllo siano entrambe controllate.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-145">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="4ff7a-146">Se sono state apportate modifiche, fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-146">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="4ff7a-147">Impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ff7a-147">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="4ff7a-148">I contenuti dei team, ad esempio file, cartelle ed elenchi, sono tutti archiviati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-148">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="4ff7a-149">Per consentire agli utenti di accedere a questi elementi nei team, le impostazioni di condivisione a livello dell'organizzazione di SharePoint devono essere consentite per la condivisione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-149">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="4ff7a-150">Le impostazioni a livello di organizzazione determinano le impostazioni disponibili per i singoli siti, inclusi i siti associati ai team.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-150">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="4ff7a-151">Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-151">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="4ff7a-152">Se si desidera consentire la condivisione di file e cartelle con persone non autenticate, scegliere **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-152">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="4ff7a-153">Se si desidera garantire che tutti gli utenti siano in grado di eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-153">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="4ff7a-154">Scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-154">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="4ff7a-156">Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ff7a-156">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="4ff7a-157">Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento a sinistra, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-157">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="4ff7a-158">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-158">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="4ff7a-159">Assicurarsi che la condivisione esterna per SharePoint sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-159">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="4ff7a-160">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-160">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="4ff7a-161">Impostazioni di collegamento predefinite a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ff7a-161">SharePoint organization level default link settings</span></span>

<span data-ttu-id="4ff7a-162">Le impostazioni predefinite per il collegamento di file e cartelle determinano l'opzione di collegamento visualizzata all'utente per impostazione predefinita quando condividono un file o una cartella.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-162">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="4ff7a-163">Gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima della condivisione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-163">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="4ff7a-164">Tenere presente che questa impostazione ha effetto su tutti i team e i siti di SharePoint dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-164">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="4ff7a-165">Scegliere il tipo di collegamento selezionato per impostazione predefinita quando gli utenti condividono file e cartelle:</span><span class="sxs-lookup"><span data-stu-id="4ff7a-165">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="4ff7a-166">**Tutti gli utenti con il collegamento** : scegliere questa opzione se si prevede di eseguire la condivisione di file e cartelle in modo molto non autenticato.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-166">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="4ff7a-167">Se si desidera consentire collegamenti a *tutti gli utenti* , ma si è preoccupati per la condivisione accidentale non autenticata, prendere in considerazione una delle altre opzioni come impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-167">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="4ff7a-168">Questo tipo di collegamento è disponibile solo se è stata abilitata la condivisione di **utenti** .</span><span class="sxs-lookup"><span data-stu-id="4ff7a-168">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="4ff7a-169">**Solo persone nell'organizzazione** : scegliere questa opzione se si prevede che la maggior parte della condivisione di file e cartelle sia con le persone all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-169">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="4ff7a-170">**Persone specifiche** : considerare questa opzione se si prevede di eseguire un sacco di condivisione di file e cartelle con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-170">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="4ff7a-171">Questo tipo di collegamento è compatibile con gli utenti e richiede l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-171">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="4ff7a-173">Per impostare le impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ff7a-173">To set the SharePoint organization level default link settings</span></span>

1. <span data-ttu-id="4ff7a-174">Passare alla pagina condivisione nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-174">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="4ff7a-175">In **collegamenti a file e cartelle**selezionare il collegamento di condivisione predefinito che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-175">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="4ff7a-176">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-176">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="4ff7a-177">Creare un team</span><span class="sxs-lookup"><span data-stu-id="4ff7a-177">Create a team</span></span>

<span data-ttu-id="4ff7a-178">Il passaggio successivo consiste nel creare il team che si intende utilizzare per la collaborazione con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-178">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="4ff7a-179">Per creare un team</span><span class="sxs-lookup"><span data-stu-id="4ff7a-179">To create a team</span></span>
1. <span data-ttu-id="4ff7a-180">In teams fare clic su **join oppure creare un team** nella parte inferiore del riquadro sinistro nella scheda **Teams** .</span><span class="sxs-lookup"><span data-stu-id="4ff7a-180">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="4ff7a-181">Fare clic su **Crea team**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-181">Click **Create a team**.</span></span>
3. <span data-ttu-id="4ff7a-182">Fare clic su **Crea un team da zero**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-182">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="4ff7a-183">Scegliere **privato** o **pubblico**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-183">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="4ff7a-184">Digitare un nome e una descrizione per il team, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-184">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="4ff7a-185">Fare clic su **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-185">Click **Skip**.</span></span>

<span data-ttu-id="4ff7a-186">Gli utenti verranno invitati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-186">We'll invite users later.</span></span> <span data-ttu-id="4ff7a-187">Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito di SharePoint associato al team.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-187">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="4ff7a-188">Impostazioni di condivisione a livello di sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ff7a-188">SharePoint site level sharing settings</span></span>

<span data-ttu-id="4ff7a-189">Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il team.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-189">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="4ff7a-190">Ad esempio, se si impostano le impostazioni a livello di organizzazione per tutti gli **utenti**, ma si desidera che tutti gli ospiti eseguano l'autenticazione per questo team, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su **Guest nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-190">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="4ff7a-192">Per impostare le impostazioni di condivisione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="4ff7a-192">To set site-level sharing settings</span></span>
1. <span data-ttu-id="4ff7a-193">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-193">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="4ff7a-194">Selezionare il sito del team appena creato.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-194">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="4ff7a-195">Sulla barra multifunzione fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-195">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="4ff7a-196">Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-196">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="4ff7a-197">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-197">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="4ff7a-198">Invitare utenti</span><span class="sxs-lookup"><span data-stu-id="4ff7a-198">Invite users</span></span>

<span data-ttu-id="4ff7a-199">Le impostazioni di condivisione Guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e ospiti al team.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-199">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="4ff7a-200">Per invitare gli utenti interni a un team</span><span class="sxs-lookup"><span data-stu-id="4ff7a-200">To invite internal users to a team</span></span>
1. <span data-ttu-id="4ff7a-201">Nel team, fare clic su **altre opzioni** (**\*\***), quindi fare clic su **Aggiungi membro**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-201">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="4ff7a-202">Digitare il nome della persona che si desidera invitare.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-202">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="4ff7a-203">Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-203">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="4ff7a-204">Per invitare gli ospiti a un team</span><span class="sxs-lookup"><span data-stu-id="4ff7a-204">To invite guests to a team</span></span>
1. <span data-ttu-id="4ff7a-205">Nel team, fare clic su **altre opzioni** (**\*\***), quindi fare clic su **Aggiungi membro**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-205">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="4ff7a-206">Digitare l'indirizzo di posta elettronica dell'ospite che si desidera invitare.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-206">Type the email address of the guest who you want to invite.</span></span>
3. <span data-ttu-id="4ff7a-207">Fare clic su **modifica informazioni Guest**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-207">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="4ff7a-208">Digitare il nome completo dell'ospite e fare clic sul segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-208">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="4ff7a-209">Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4ff7a-209">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ff7a-210">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4ff7a-210">See Also</span></span>

[<span data-ttu-id="4ff7a-211">Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati</span><span class="sxs-lookup"><span data-stu-id="4ff7a-211">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="4ff7a-212">Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="4ff7a-212">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="4ff7a-213">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="4ff7a-213">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="4ff7a-214">[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).</span><span class="sxs-lookup"><span data-stu-id="4ff7a-214">[Create a B2B extranet with managed guests](b2b-extranet.md)</span></span>
