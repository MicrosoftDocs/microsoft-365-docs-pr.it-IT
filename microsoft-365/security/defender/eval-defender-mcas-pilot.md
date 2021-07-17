---
title: Progetti Microsoft Cloud App Security con Microsoft 365 Defender, creare gruppi pilota, configurare il controllo dell'accesso condizionale, provare le funzionalità, configurare come parte di Microsoft 365 Defender
description: Configurare il laboratorio di Microsoft 365 Defender o l'ambiente pilota per testare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458047"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a>Progetti pilota Microsoft Cloud App Security con Microsoft 365 Defender


**Si applica a:**
- Microsoft 365 Defender

Questo articolo è [il passaggio 3 di 3 nel](eval-defender-mcas-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Cloud App Security. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-mcas-overview.md).

Utilizzare la procedura seguente per configurare il progetto pilota per Microsoft Cloud App Security.


![Passaggi per la distribuzione pilota Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- Passaggio 1. [Creare il gruppo pilota- Ambito della distribuzione pilota per determinati gruppi di utenti](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [Passaggio 2. Configurare la protezione - Controllo app con accesso condizionale](#step-2-configure-protection--conditional-access-app-control)
- [Passaggio 3. Funzionalità di prova: esercitazioni per la protezione dell'ambiente](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a>Passaggio 1. Creare il gruppo pilota- Ambito della distribuzione pilota per determinati gruppi di utenti

Microsoft Cloud App Security consente di impostare l'ambito della distribuzione. L'ambito consente di selezionare determinati gruppi di utenti da monitorare per le app o esclusi dal monitoraggio. È possibile includere o escludere gruppi di utenti. Per l'ambito della distribuzione pilota, vedere [Distribuzione con ambito](/cloud-app-security/scoped-deployment).


## <a name="step-2-configure-protection--conditional-access-app-control"></a>Passaggio 2. Configurare la protezione - Controllo app con accesso condizionale

Una delle protezioni più potenti che puoi configurare è il controllo dell'app con accesso condizionale. Ciò richiede l'integrazione con Azure Active Directory (Azure AD). Ti consente di applicare criteri di accesso condizionale, inclusi i criteri correlati (come la richiesta di dispositivi integri), alle app cloud che hai sanzionato. 

Il primo passaggio nell'Microsoft Cloud App Security per gestire le app SaaS consiste nell'individuarle e quindi aggiungerle al tenant di Azure AD. Per assistenza con l'individuazione, vedi [Individuare e gestire le app SaaS nella rete.](/cloud-app-security/tutorial-shadow-it) Dopo aver individuato le app, [aggiungerle al tenant di Azure AD.](/azure/active-directory/manage-apps/add-application-portal)

È possibile iniziare a gestire questi elementi eseguendo le operazioni seguenti:

- Innanzitutto, in Azure AD crea un nuovo criterio di accesso condizionale e configuralo in "Usa controllo app di accesso condizionale". In questo modo la richiesta viene reindirizzata Cloud App Security. Puoi creare un criterio e aggiungere tutte le app SaaS a questo criterio.
- Successivamente, in Cloud App Security creare i criteri di sessione. Creare un criterio per ogni controllo che si desidera applicare.

Per altre informazioni, incluse le app e i client supportati, vedi Proteggere le [app Microsoft Cloud App Security controllo dell'app di accesso condizionale.](/cloud-app-security/proxy-intro-aad) 

Ad esempio, vedere [Criteri di Microsoft Cloud App Security consigliati per le app SaaS.](../office-365-security/mcas-saas-access-policies.md) Questi criteri si basano su un set di [criteri](../office-365-security/microsoft-365-policies-configurations.md) comuni di identità e accesso ai dispositivi consigliati come punto di partenza per tutti i clienti. 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a>Passaggio 3. Funzionalità di prova: esercitazioni per la protezione dell'ambiente 

La Microsoft Cloud App Security include una serie di esercitazioni per individuare i rischi e proteggere l'ambiente. 

Provare Cloud App Security esercitazioni:

- [Rilevare attività utente sospette](/cloud-app-security/tutorial-suspicious-activity)
- [Analizzare gli utenti rischiosi](/cloud-app-security/tutorial-ueba)
- [Analizzare le app OAuth rischiose](/cloud-app-security/investigate-risky-oauth)
- [Individuare e proteggere le informazioni riservate](/cloud-app-security/tutorial-dlp)
- [Proteggere qualsiasi app nell'organizzazione in tempo reale](/cloud-app-security/tutorial-proxy)
- [Bloccare i download di informazioni riservate](/cloud-app-security/use-case-proxy-block-session-aad)
- [Proteggere i file con la quarantena dell'amministratore](/cloud-app-security/use-case-admin-quarantine)
- [Richiedere l'autenticazione dettagliata in base a un'azione rischiosa](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a>Passaggi successivi

[Analizzare e rispondere usando Microsoft 365 Defender in un ambiente pilota](eval-defender-investigate-respond.md)

Tornare alla panoramica di [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)