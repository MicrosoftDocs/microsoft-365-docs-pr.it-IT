---
title: Configurare Microsoft Viva Learning (anteprima) nell'Teams di amministrazione
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
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
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636135"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Configurare Microsoft Viva Learning (anteprima) nell'Teams di amministrazione

> [!NOTE]
> Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente. 

L Teams admin installa Viva Learning (Preview) e applica i criteri di autorizzazione tramite l'Teams di amministrazione.

1. Per Viva Learning (Anteprima), devi prima impostare i criteri di aggiornamento in Teams. Per ulteriori informazioni, vedere [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Accedere all'interfaccia Teams di amministrazione.

    2. Selezionare **Teams**  >  **Criteri di aggiornamento**.

    3. Selezionare **Aggiungi**. 

    4. Assegnare un nome al criterio di aggiornamento, aggiungere un criterio e attivare **Mostra funzionalità di anteprima.**

2. L'amministratore deve informare gli utenti dell'aggiornamento dei criteri in modo che spostino la build nell'anteprima pubblica per Teams. 

    1. Gli utenti devono selezionare l'immagine del > **informazioni**  >  **sull'anteprima pubblica.**
   
        ![Spostamento superiore nell'Teams che mostra il profilo dell'utente](../media/learning/learning-app-select-profile-teams.png)
    
    2. Gli utenti devono accettare i **termini e le condizioni di anteprima** pubblica.

        ![Passare alla build di anteprima pubblica](../media/learning/learning-app-switch-to-public-preview.png)
 
3. Per le organizzazioni che hanno criteri restrittivi e devono abilitare Viva Learning (Preview), seguire il processo nella sezione successiva.

## <a name="manage-settings-for-viva-learning-preview"></a>Gestire le impostazioni per Viva Learning (anteprima)

Per eseguire queste attività, è Teams amministratore dell'interfaccia di amministrazione.

Per rendere Viva Learning (Anteprima) disponibile per gli utenti dell'organizzazione, attenersi alla seguente procedura:

1. Nel riquadro di spostamento sinistro dell'Teams di amministrazione passare a Teams  >  **app Gestisci app**.

   ![Spostamento a sinistra nell'Teams di amministrazione che mostra le Teams app e la sezione Gestisci app.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. Nella casella **di ricerca della** pagina Gestisci app digitare Viva *learning* e quindi selezionare Viva **Learning (anteprima).**

   ![Pagina Gestisci app nell'interfaccia Teams di amministrazione che mostra la casella di ricerca.](../media/learning/learning-app-teams-manage-apps-page.png)

3. Nella pagina **Viva Learning (Anteprima):**

   1. In **Stato** seleziona **Consentito per** attivare Viva Learning (Anteprima).

   2. Nella scheda **Impostazioni,** in **Impostazioni app,** passare all'interfaccia di amministrazione Microsoft 365 per [configurare le origini di contenuto didattiche.](content-sources-365-admin-center.md)

   ![Pagina Di apprendimento nell'Teams di amministrazione che mostra la sezione Impostazioni stato e app.](../media/learning/learning-app-teams-learning-page.png)

4. Dopo Gestire le impostazioni   **dell'app,** vai a Criteri di autorizzazione e Criteri di installazione per concedere l'autorizzazione ai dipendenti che devono avere accesso a Viva Learning (Preview) come parte della partecipazione dell'organizzazione all'anteprima.

> [!NOTE]
>  Se l'organizzazione si trova nel Circuito 4.0 come parte del programma TAP100 di Teams, potrebbe essere necessario abilitare gli utenti approvati nel Circuito 3.0 per accedere a Viva Learning (Anteprima). <br><br>Come parte dell'anteprima, Viva Learning (Preview) viene rilasciato nel Circuito 3.0. Se l'organizzazione si trova nel Circuito 4.0, viva learning (anteprima) non verrà visualizzato nella **pagina Gestisci** app. Per testare l'app, devi creare un criterio di autorizzazione per le app personalizzate, impostarlo su Consenti tutte le app e assegnarlo agli utenti approvati di Ring 3.0. <br><br>   ![Tap-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Passaggio successivo

[Configurare le origini di contenuto di apprendimento per Viva Learning (anteprima) nell'Microsoft 365 di amministrazione](content-sources-365-admin-center.md)
