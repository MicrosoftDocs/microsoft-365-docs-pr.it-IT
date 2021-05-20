---
title: Indagare sugli utenti Microsoft 365 Defender
description: Indagare sugli utenti per un incidente nel centro Microsoft 365 sicurezza di 200.
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, segnalare, identità, dati, dispositivi, app, incidente, analizzare, rispondere
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572802"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Indagare sugli utenti Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

Parte dell'indagine sugli incidenti può includere account utente. Iniziare con la **scheda Utenti** per un incidente da Incidenti & **avvisi >** *incidente* **> Utenti**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Esempio di pagina Utenti per un incidente":::

Per ottenere un breve riepilogo di un account utente per l'incidente, selezionare il segno di spunta accanto al nome dell'account utente. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Esempio del riquadro di riepilogo dell'account utente per un incidente nel centro Microsoft 365 sicurezza di applicazione":::

> [!NOTE]
> La pagina Utente mostra Azure Active Directory organizzazione di Azure AD e gruppi, che consente di comprendere i gruppi e le autorizzazioni associati a un utente.

In questa pagina a comparsa è possibile esaminare le informazioni sulle minacce degli utenti, inclusi eventuali incidenti correnti, avvisi attivi e livello di rischio, nonché l'esposizione degli utenti, account, dispositivi e altro ancora.

Inoltre, è possibile intervenire direttamente nel centro sicurezza Microsoft 365 per rivolgersi a un utente compromesso, confermando che l'utente è compromesso o richiedendo loro di accedere di nuovo.

Da qui, è possibile selezionare **Vai alla pagina utente** per visualizzare i dettagli di un account utente. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Esempio della pagina dell'account utente per un incidente nel centro Microsoft 365 sicurezza di applicazione":::

È inoltre possibile visualizzare questa pagina selezionando il nome dell'account utente dall'elenco nella **pagina** Utenti.

La Microsoft 365 utente del Centro sicurezza locale combina le informazioni di Microsoft Defender for Endpoint, Microsoft Defender for Identity e Microsoft Cloud App Security (a seconda delle licenze in diserti). 

Questa pagina mostra informazioni specifiche del rischio per la sicurezza di un account utente. Ciò include un punteggio che aiuta a valutare il rischio e gli eventi e gli avvisi recenti che hanno contribuito al rischio complessivo dell'utente.

Da questa pagina è possibile eseguire queste azioni aggiuntive: 

- Contrassegnare l'account utente come compromesso
- Richiedere all'utente di accedere di nuovo
- Sospendere l'account utente
- Visualizzare le impostazioni Azure Active Directory account utente di Azure AD (Azure AD)
- Visualizzare i file di proprietà dell'account utente
- Visualizzare i file condivisi con l'utente. 

Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Esempio delle azioni su un account utente per un incidente nel centro Microsoft 365 sicurezza di sicurezza":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Passaggi successivi

Se necessario per gli incidenti in corso, continuare [l'indagine](investigate-incidents.md).

## <a name="see-also"></a>Vedere anche

- [Panoramica sugli incidenti](incidents-overview.md)
- [Assegnare priorità agli incidenti](incident-queue.md)
- [Gestire gli incidenti](manage-incidents.md)