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
description: Informazioni su come configurare Microsoft Viva Learning (Anteprima) nell'Teams di amministrazione.
ms.openlocfilehash: 860f16bee7d93f2212072c5d738263402704272f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789232"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Configurare Microsoft Viva Learning (anteprima) nell'Teams di amministrazione

> [!NOTE]
> Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente. 

L Teams amministratore deve eseguire alcuni passaggi per abilitare Viva Learning (Preview) per gli utenti nel tenant. Questi passaggi variano in base alla modalità di a attivazione del tenant: [*Anteprima*](set-up-teams-admin-center.md#public-preview-tenants) pubblica [ *o Anteprima privata* (o Beta).](set-up-teams-admin-center.md#private-preview-tenants)

## <a name="public-preview-tenants"></a>Tenant di anteprima pubblica

### <a name="administrator-steps-for-public-preview-tenants"></a>Passaggi dell'amministratore per i tenant di anteprima pubblica

Poiché Viva Learning (Anteprima) non è ancora disponibile in genere, sono necessari alcuni passaggi per abilitare le funzionalità e impostare le autorizzazioni per utenti o gruppi specifici. 

1. Abilita le funzionalità di anteprima pubblica per gli utenti viva learning (anteprima).

    a. Modificare Teams di aggiornamento per abilitare le funzionalità di anteprima pubblica. Vedi [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).

    b. Abilitare i criteri di aggiornamento per gli utenti o i gruppi che eseguiranno il test Viva Learning (Anteprima). Vedere [Assegnare criteri a utenti e gruppi.](/microsoftteams/assign-policies-users-and-groups)

2. Modifica i criteri di autorizzazione dell'app per gli utenti viva learning (anteprima).

    a. A meno che non sia attualmente parte del criterio globale, consenti tutte le app Microsoft nei criteri di autorizzazione delle app. Vedi [Gestire i criteri di autorizzazione delle app in Microsoft Teams](/microsoftteams/teams-app-permission-policies). 

    b. Abilita i criteri di autorizzazione dell'app per gli utenti o i gruppi che eseguiranno il test Viva Learning (Anteprima). Vedere [Assegnare criteri a utenti e gruppi.](/microsoftteams/assign-policies-users-and-groups)

3.  Informare gli utenti che testeranno Viva Learning (Preview) di passare dal client di [compilazione all'anteprima pubblica per Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).

> [!IMPORTANT]
> Per i tenant di anteprima pubblica, Viva Learning (Anteprima) non verrà visualizzato **nelle** app gestite nell'interfaccia di amministrazione di Teams fino al rilascio finale del prodotto. Tuttavia, gli utenti abilitati per l'anteprima pubblica possono trovare Viva Learning (Anteprima) nell'app store di Teams e usarlo, dopo aver configurato i criteri e le autorizzazioni corretti.

### <a name="user-steps-for-public-preview-tenants"></a>Passaggi utente per i tenant di anteprima pubblica

Gli utenti abilitati per il test dell'anteprima pubblica, abilitando i criteri descritti [in](/microsoftteams/public-preview-doc-updates#enable-public-preview) [precedenza,](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) devono passare all'anteprima pubblica nel Teams client.

1. Gli utenti devono selezionare l'immagine del > **informazioni**  >  **sull'anteprima pubblica.**
   
    ![Spostamento superiore nell'Teams che mostra il profilo dell'utente](../media/learning/learning-app-select-profile-teams.png)
    
2. Gli utenti devono accettare i termini e le condizioni dell'anteprima pubblica.

    ![Passare alla build di anteprima pubblica](../media/learning/learning-app-switch-to-public-preview.png)
 
3. Gli utenti possono ora trovare Viva Learning (Anteprima) nel Teams app store e iniziare a usarlo.

## <a name="private-preview-tenants"></a>Tenant di anteprima privati

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a>Passaggi dell'amministratore per i tenant di Anteprima privata (o Beta)

Per i tenant di anteprima privata, non è necessario che siano abilitati altri criteri. Tuttavia, Viva Learning (Anteprima) deve essere reso disponibile per gli utenti dell'organizzazione.

1. Nel riquadro di spostamento sinistro dell'Teams di amministrazione passare a Teams  >  **app Gestisci app**.

   ![Spostamento a sinistra nell'Teams di amministrazione che mostra le Teams app e la sezione Gestisci app.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. Nella casella **di ricerca della** pagina Gestisci app digitare Viva *Learning* e quindi selezionare Viva **Learning (anteprima).**

   ![Pagina Gestisci app nell'interfaccia Teams di amministrazione che mostra la casella di ricerca.](../media/learning/learning-app-teams-manage-apps-page.png)

3. Nella pagina **Viva Learning (anteprima),** in **Stato,** selezionare **Consentito** per attivare Viva Learning (anteprima).

   ![Pagina Di apprendimento nell'Teams di amministrazione che mostra la sezione Impostazioni stato e app.](../media/learning/learning-app-teams-learning-page.png)


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

## <a name="next-step"></a>Passaggio successivo

[Configurare le origini di contenuto di apprendimento per Viva Learning (anteprima) nell'Microsoft 365 di amministrazione](content-sources-365-admin-center.md)
