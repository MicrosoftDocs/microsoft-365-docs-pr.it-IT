---
title: Configurare Microsoft Viva Learning (anteprima) nell'interfaccia di amministrazione di Teams
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Informazioni su come configurare Microsoft Viva Learning (Anteprima) nell'interfaccia di amministrazione di Teams.
ms.openlocfilehash: 40e659796b22097f42515c0cbb704bdaa4ccc972
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333519"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Configurare Microsoft Viva Learning (anteprima) nell'interfaccia di amministrazione di Teams

> [!NOTE]
> Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente. 

L'amministratore di Teams installa Viva Learning (Anteprima) e applica i criteri di autorizzazione tramite l'interfaccia di amministrazione di Teams.

## <a name="manage-settings-for-viva-learning-preview"></a>Gestire le impostazioni per Viva Learning (anteprima)

Per eseguire queste attività, è necessario essere un amministratore nell'interfaccia di amministrazione di Teams.

Per rendere Viva Learning (Anteprima) disponibile per gli utenti dell'organizzazione, attenersi alla seguente procedura:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare a **App di Teams** Gestisci  >  **app.**

   ![Spostamento a sinistra nell'interfaccia di amministrazione di Teams che mostra le app di Teams e la sezione Gestisci app.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. Nella casella **di ricerca della** pagina Gestisci app digitare Viva *learning* e quindi selezionare Viva **Learning (anteprima).**

   ![Pagina Gestisci app nell'interfaccia di amministrazione di Teams che mostra la casella di ricerca.](../media/learning/learning-app-teams-manage-apps-page.png)

3. Nella pagina **Viva Learning (Anteprima):**

   1. In **Stato** seleziona **Consentito per** attivare Viva Learning (Anteprima).

   2. Nella scheda **Impostazioni,** in **Impostazioni app,** passare all'interfaccia di amministrazione di Microsoft 365 per [configurare le origini di contenuto didattiche.](content-sources-365-admin-center.md)

   ![Pagina Di apprendimento nell'interfaccia di amministrazione di Teams con la sezione Impostazioni stato e app.](../media/learning/learning-app-teams-learning-page.png)

4. Dopo Gestire le impostazioni   **dell'app,** vai a Criteri di autorizzazione e Criteri di installazione per concedere l'autorizzazione ai dipendenti che devono avere accesso a Viva Learning (Preview) come parte della partecipazione dell'organizzazione all'anteprima.

> [!NOTE]
>  Se l'organizzazione si trova nel Circuito 4.0 come parte del programma TAP100 di Teams, potrebbe essere necessario consentire agli utenti approvati nel Circuito 3.0 di accedere a Viva Learning (Anteprima). <br><br>Come parte dell'anteprima, Viva Learning (Preview) viene rilasciato nel Circuito 3.0. Se l'organizzazione si trova nel Circuito 4.0, viva learning (anteprima) non verrà visualizzato nella **pagina Gestisci** app. Per testare l'app, devi creare un criterio di autorizzazione per le app personalizzate, impostarlo su Consenti tutte le app e assegnarlo agli utenti approvati di Ring 3.0. <br><br>   ![Tap-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Passaggio successivo

[Configurare le origini di contenuto di apprendimento per Viva Learning (Anteprima) nell'interfaccia di amministrazione di Microsoft 365](content-sources-365-admin-center.md)