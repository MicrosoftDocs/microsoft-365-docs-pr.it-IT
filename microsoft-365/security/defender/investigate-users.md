---
title: Analizzare gli utenti nel Centro sicurezza Microsoft 365
description: Analizzare gli utenti nel Centro sicurezza Microsoft 365
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, segnalare, identità, dati, dispositivi, app, eventi imprevisti, analizzare, risposta
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
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939731"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a>Analizzare gli utenti nel Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

Parte dell'analisi degli eventi imprevisti può includere account utente. Iniziare con la **scheda Utenti** per un evento imprevisto da **Eventi imprevisti & avvisi >** evento *>* **utenti**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Esempio di pagina Utenti per un evento imprevisto":::

Per ottenere un breve riepilogo di un account utente per l'evento imprevisto, selezionare il segno di spunta accanto al nome dell'account utente. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Esempio del riquadro di riepilogo dell'account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::

Da qui puoi selezionare **Vai alla pagina utente** per visualizzare i dettagli di un account utente. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Esempio di pagina dell'account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::

Puoi anche visualizzare questa pagina selezionando il nome dell'account utente nell'elenco nella **pagina** Utenti.

La pagina utente del Centro sicurezza Microsoft 365 combina le informazioni di Microsoft Defender for Endpoint, Microsoft Defender for Identity e Microsoft Cloud App Security (a seconda delle licenze di cui si dispone). 

In questa pagina vengono visualizzate informazioni specifiche del rischio per la sicurezza di un account utente. Include un punteggio che consente di valutare i rischi e gli eventi e gli avvisi recenti che hanno contribuito al rischio complessivo dell'utente.

Da questa pagina puoi eseguire queste azioni aggiuntive: 

- Contrassegnare l'account utente come compromesso
- Richiedere all'utente di eseguire di nuovo l'accesso
- Sospendere l'account utente
- Vedere le impostazioni dell'account utente di Azure Active Directory (Azure AD)
- Visualizzare i file di proprietà dell'account utente
- Visualizzare i file condivisi con questo utente. 

Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Esempio di azioni su un account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica sugli incidenti](incidents-overview.md)
- [Assegnare priorità agli incidenti](incident-queue.md)
- [Gestire gli incidenti](manage-incidents.md)