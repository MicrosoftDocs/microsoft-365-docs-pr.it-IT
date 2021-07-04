---
title: Configurare Microsoft Viva Learning (anteprima) nell'Teams di amministrazione
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Informazioni su come configurare Microsoft Viva Learning (anteprima) nell'Teams di amministrazione.
ms.openlocfilehash: 99e63210e8f8c10e3721c35fb69df7880c7e1929
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290220"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="45fc4-103">Configurare Microsoft Viva Learning (anteprima) nell'Teams di amministrazione</span><span class="sxs-lookup"><span data-stu-id="45fc4-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="45fc4-104">Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="45fc4-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="45fc4-105">L Teams amministratore deve eseguire alcuni passaggi per abilitare Viva Learning (Anteprima) per gli utenti nel tenant.</span><span class="sxs-lookup"><span data-stu-id="45fc4-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="45fc4-106">Questi passaggi variano in base alla modalità di a attivazione del tenant: [*Anteprima*](set-up-teams-admin-center.md#public-preview-tenants) pubblica [ *o Anteprima privata* (o Beta).](set-up-teams-admin-center.md#private-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="45fc4-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="45fc4-107">Tenant di anteprima pubblica</span><span class="sxs-lookup"><span data-stu-id="45fc4-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="45fc4-108">Passaggi dell'amministratore per i tenant di anteprima pubblica</span><span class="sxs-lookup"><span data-stu-id="45fc4-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="45fc4-109">Poiché viva Learning (anteprima) non è ancora disponibile in genere, sono necessari alcuni passaggi per abilitare le funzionalità e impostare le autorizzazioni per utenti o gruppi specifici.</span><span class="sxs-lookup"><span data-stu-id="45fc4-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="45fc4-110">Abilita le funzionalità di anteprima pubblica per gli utenti viva Learning (anteprima).</span><span class="sxs-lookup"><span data-stu-id="45fc4-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="45fc4-111">a.</span><span class="sxs-lookup"><span data-stu-id="45fc4-111">a.</span></span> <span data-ttu-id="45fc4-112">Modificare Teams di aggiornamento per abilitare le funzionalità di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="45fc4-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="45fc4-113">Vedi [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span><span class="sxs-lookup"><span data-stu-id="45fc4-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="45fc4-114">b.</span><span class="sxs-lookup"><span data-stu-id="45fc4-114">b.</span></span> <span data-ttu-id="45fc4-115">Abilitare i criteri di aggiornamento per gli utenti o i gruppi che eseguiranno il test Viva Learning (anteprima).</span><span class="sxs-lookup"><span data-stu-id="45fc4-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="45fc4-116">Vedere [Assegnare criteri a utenti e gruppi.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="45fc4-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="45fc4-117">Modifica i criteri di autorizzazione dell'app per gli utenti viva Learning (anteprima).</span><span class="sxs-lookup"><span data-stu-id="45fc4-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="45fc4-118">a.</span><span class="sxs-lookup"><span data-stu-id="45fc4-118">a.</span></span> <span data-ttu-id="45fc4-119">A meno che non sia attualmente parte del criterio globale, consenti tutte le app Microsoft nei criteri di autorizzazione delle app.</span><span class="sxs-lookup"><span data-stu-id="45fc4-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="45fc4-120">Vedi [Gestire i criteri di autorizzazione delle app in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="45fc4-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="45fc4-121">b.</span><span class="sxs-lookup"><span data-stu-id="45fc4-121">b.</span></span> <span data-ttu-id="45fc4-122">Abilita i criteri di autorizzazione dell'app per gli utenti o i gruppi che eseguiranno il test viva Learning (anteprima).</span><span class="sxs-lookup"><span data-stu-id="45fc4-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="45fc4-123">Vedere [Assegnare criteri a utenti e gruppi.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="45fc4-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3. <span data-ttu-id="45fc4-124">Informare gli utenti che testeranno Viva Learning (Anteprima) di passare al client di compilazione [in Anteprima pubblica per Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span><span class="sxs-lookup"><span data-stu-id="45fc4-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45fc4-125">Per i tenant di anteprima pubblica, Viva Learning (Anteprima) non verrà visualizzato **nelle** app gestite nell'interfaccia di amministrazione di Teams fino al rilascio finale del prodotto.</span><span class="sxs-lookup"><span data-stu-id="45fc4-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="45fc4-126">Tuttavia, gli utenti abilitati per l'anteprima pubblica possono trovare Viva Learning (Anteprima) nell'app store di Teams e usarlo, dopo aver configurato i criteri e le autorizzazioni corretti.</span><span class="sxs-lookup"><span data-stu-id="45fc4-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="45fc4-127">Passaggi utente per i tenant di anteprima pubblica</span><span class="sxs-lookup"><span data-stu-id="45fc4-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="45fc4-128">Gli utenti abilitati per il test dell'anteprima pubblica, abilitando i criteri descritti [in](/microsoftteams/public-preview-doc-updates#enable-public-preview) [precedenza,](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) devono passare all'anteprima pubblica nel Teams client.</span><span class="sxs-lookup"><span data-stu-id="45fc4-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="45fc4-129">Gli utenti devono selezionare l'immagine del > **informazioni**  >  **sull'anteprima pubblica.**</span><span class="sxs-lookup"><span data-stu-id="45fc4-129">Users must select their profile image > **About** > **Public Preview**.</span></span>

    ![Spostamento superiore nell'Teams che mostra il profilo dell'utente](../media/learning/learning-app-select-profile-teams.png)

2. <span data-ttu-id="45fc4-131">Gli utenti devono accettare i termini e le condizioni dell'anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="45fc4-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![Passare alla build di anteprima pubblica](../media/learning/learning-app-switch-to-public-preview.png)

3. <span data-ttu-id="45fc4-133">Gli utenti possono ora trovare Viva Learning (anteprima) nell'app store Teams e iniziare a usarlo.</span><span class="sxs-lookup"><span data-stu-id="45fc4-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="45fc4-134">Tenant di anteprima privati</span><span class="sxs-lookup"><span data-stu-id="45fc4-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="45fc4-135">Passaggi dell'amministratore per i tenant di Anteprima privata (o Beta)</span><span class="sxs-lookup"><span data-stu-id="45fc4-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="45fc4-136">Per i tenant di anteprima privata, non è necessario che siano abilitati altri criteri.</span><span class="sxs-lookup"><span data-stu-id="45fc4-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="45fc4-137">Tuttavia, Viva Learning (Anteprima) deve essere reso disponibile per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="45fc4-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="45fc4-138">Nel riquadro di spostamento sinistro dell'Teams di amministrazione passare a Teams  >  **app Gestisci app**.</span><span class="sxs-lookup"><span data-stu-id="45fc4-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Spostamento a sinistra nell'Teams di amministrazione che mostra le Teams app e la sezione Gestisci app.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="45fc4-140">Nella casella **di ricerca della** pagina Gestisci app digitare Viva *Learning* e quindi selezionare Viva **Learning (anteprima).**</span><span class="sxs-lookup"><span data-stu-id="45fc4-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Pagina Gestisci app nell'interfaccia Teams di amministrazione che mostra la casella di ricerca.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="45fc4-142">Nella pagina **Viva Learning (anteprima),** in **Stato,** **selezionare** Consentito per attivare Viva Learning (anteprima).</span><span class="sxs-lookup"><span data-stu-id="45fc4-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![Learning nell'interfaccia Teams di amministrazione che mostra la sezione Impostazioni stato e app.](../media/learning/learning-app-teams-learning-page.png)

<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a><span data-ttu-id="45fc4-144">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="45fc4-144">Next step</span></span>

[<span data-ttu-id="45fc4-145">Configurare le origini di contenuto di apprendimento per Viva Learning (Anteprima) nella interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45fc4-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
