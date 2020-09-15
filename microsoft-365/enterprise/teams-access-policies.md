---
title: Criteri dei team consigliati-Microsoft 365 per Enterprise | Documenti Microsoft
description: Vengono descritti i criteri per i suggerimenti Microsoft su come proteggere le comunicazioni dei team e l'accesso ai file.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/12/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: fc2b83fc167a9385383d7085ed6d1e8db15abd42
ms.sourcegitcommit: a13f43a3e981c90f1e0b9805c9c16a56f67fc650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651133"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Suggerimenti sui criteri per la protezione di chat, gruppi e file di Team

In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per proteggere le chat, i gruppi e i contenuti di Microsoft teams, ad esempio file e calendari. Queste linee guida si basano sui [criteri comuni di accesso a identità e dispositivi](identity-access-policies.md), con informazioni aggiuntive specifiche per le squadre. Poiché i team si integrano con gli altri prodotti, vedere anche [consigli sui criteri per la protezione di siti e file di SharePoint](sharepoint-file-access-policies.md) e [Suggerimenti per i criteri per la protezione della posta elettronica](secure-email-recommended-policies.md).

Tali raccomandazioni si basano su tre diversi livelli di sicurezza e protezione per i team che possono essere applicati in base alla granularità delle proprie esigenze: linea di base, sensibile e altamente regolamentata. Per ulteriori informazioni su questi livelli di sicurezza e sui criteri consigliati, fare riferimento a questi suggerimenti nelle [configurazioni di identità e accesso ai dispositivi](microsoft-365-policies-configurations.md).

Ulteriori suggerimenti specifici per la distribuzione dei team sono inclusi in questo articolo per coprire specifiche condizioni di autenticazione, ad esempio per gli utenti esterni all'organizzazione. Sarà necessario seguire queste linee guida per un'esperienza di sicurezza completa.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Guida introduttiva ai team prima di altri servizi dipendenti

Non è necessario abilitare i servizi dipendenti per iniziare a utilizzare Microsoft teams. Questi saranno tutti "solo lavoro". Tuttavia, è necessario essere pronti a gestire quanto segue:

- Gruppi di Microsoft 365
- Siti del team di SharePoint
- OneDrive for Business
- Cassette postali di Exchange
- Flussi video e piani di pianificazione (se questi servizi sono abilitati)

## <a name="updating-common-policies-to-include-teams"></a>Aggiornamento di criteri comuni per l'inclusione di Team

Per proteggere la chat, i gruppi e il contenuto nei team, nel diagramma seguente vengono illustrati i criteri da aggiornare dai criteri di identità e accesso ai dispositivi comuni. Affinché ogni criterio venga aggiornato, assicurarsi che i team e i servizi dipendenti siano inclusi nell'assegnazione delle app cloud.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso ai team e ai servizi dipendenti](../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[Visualizzazione di una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Questi sono i servizi dipendenti da includere nell'assegnazione delle app cloud per i team:

- Microsoft Teams
- SharePoint e OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (registrazioni di riunioni)
- Microsoft Planner (attività di pianificazione e pianificazione dei dati)

In questa tabella sono elencati i criteri che è necessario rivisitare e i collegamenti a ogni criterio nei [criteri di identità e accesso ai dispositivi comuni](identity-access-policies.md), che include il set di criteri più ampio per tutte le applicazioni di Office.

|Livello di protezione|Criteri|Ulteriori informazioni per l'implementazione di Teams|
|:---------------|:-------|:----------------|
|**Protezione di base**|[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Assicurarsi che i team e i servizi dipendenti siano inclusi nell'elenco delle app. I team dispongono di regole di accesso guest e di accesso esterno da prendere in considerazione, per ulteriori informazioni, vedere più avanti in questo articolo.|
|        |[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Includere team e servizi dipendenti nell'assegnazione delle app cloud.|
|        |[Gli utenti a rischio elevato devono modificare la password](identity-access-policies.md#high-risk-users-must-change-password)|Costringe gli utenti dei team a modificare la propria password quando si effettua l'accesso se viene rilevata un'attività ad alto rischio per il proprio account. Assicurarsi che i team e i servizi dipendenti siano inclusi nell'elenco delle app.|
|        |[Applicare i criteri di protezione dei dati dell'APP](identity-access-policies.md#apply-app-data-protection-policies)|Assicurarsi che i team e i servizi dipendenti siano inclusi nell'elenco delle app. Aggiornare i criteri per ogni piattaforma (iOS, Android, Windows).|
|        |[Richiedere applicazioni approvate e protezione delle APP](identity-access-policies.md#require-approved-apps-and-app-protection)|Includere team e servizi dipendenti in questo criterio.|
|        |[Definire i criteri di conformità del dispositivo](identity-access-policies.md#define-device-compliance-policies)|Includere team e servizi dipendenti in questo criterio.|
|        |[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere team e servizi dipendenti in questo criterio.|
|**Sensibili**|[Richiedere l'AMF quando il rischio di accesso è *basso*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|I team dispongono di regole di accesso guest e di accesso esterno da prendere in considerazione, per ulteriori informazioni, vedere più avanti in questo articolo. Includere team e servizi dipendenti in questo criterio.|
|         |[Richiedere PC conformi *e* dispositivi mobili](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere team e servizi dipendenti in questo criterio.|
|**Riservatezza elevata**|[Richiede *sempre* l'autenticazione Master](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Indipendentemente dall'identità dell'utente, l'AMF verrà utilizzata dall'organizzazione. Includere team e servizi dipendenti in questo criterio.
| | |

## <a name="teams-dependent-services-architecture"></a>Architettura dei servizi dipendenti dai team

Per informazioni di riferimento, nel diagramma seguente vengono illustrati i team di servizi su cui si basa. Per ulteriori informazioni e altre illustrazioni, vedere [Microsoft Teams and related Productivity Services in microsoft 365 for it Architects](../solutions/productivity-illustrations.md).

![Diagramma che mostra le dipendenze dei team in SharePoint, OneDrive for business ed Exchange](../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Abilitazione dell'accesso guest e esterno per i team

In Azure AD, gli utenti guest e External sono gli stessi. Il tipo di utente per entrambi è Guest. Gli utenti Guest sono utenti B2B. Microsoft teams differenzia tra gli utenti guest e gli utenti esterni nell'app. Anche se è importante comprendere in che modo ognuno di questi viene trattato in teams, entrambi i tipi di utenti sono utenti B2B in Azure AD e i criteri consigliati per gli utenti B2B sono validi per entrambi. Per i criteri consigliati per consentire l'accesso guest, vedere [criteri per consentire l'accesso guest ed esterno B2B](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Accesso guest in Teams

Oltre ai criteri per gli utenti interni all'azienda o all'organizzazione, gli amministratori possono abilitare l'accesso guest per consentire, a livello di utente, le persone esterne alla propria azienda o all'organizzazione per accedere alle risorse dei team e interagire con gli utenti interni per operazioni quali conversazioni di gruppo, chat e riunioni. Per ulteriori informazioni sull'accesso guest, vedere il seguente collegamento: [Teams Guest Access](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Accesso esterno in teams

L'accesso esterno a volte è confuso con l'accesso guest, quindi è importante essere chiaro che questi due meccanismi di accesso non interno sono in realtà molto diversi. Mentre l'accesso Guest si verifica in base ai singoli utenti (è possibile aggiungere un utente alla volta), quando un amministratore abilita l'accesso esterno, consente di aggiungere contemporaneamente tutti gli utenti di un dominio esterno ai team. Tuttavia, gli utenti esterni hanno meno accesso e funzionalità di quelli che sono stati aggiunti tramite accesso guest. Gli utenti di accessi esterni possono chattare con gli utenti interni tramite Team.

Per ulteriori informazioni sull'accesso esterno e su come implementarla se necessario, consultare [gestione dell'accesso esterno in Microsoft teams](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>Criteri per i team

Al di fuori dei criteri comuni sopra elencati, esistono criteri specifici per le squadre che possono e devono essere configurati per gestire diverse funzionalità dei team.

### <a name="teams-and-channels-policies"></a>Criteri per team e canali

I team e i canali sono due elementi comunemente utilizzati in Microsoft teams e esistono criteri che è possibile applicare per controllare quali utenti possono o non possono eseguire quando si utilizzano Team e canali. Anche se è possibile creare un team globale, se l'organizzazione dispone di 5000 utenti o meno, è probabile che sia utile disporre di team e canali di dimensioni ridotte per scopi specifici, in linea con le proprie esigenze organizzative.

Se si desidera modificare il criterio predefinito o creare criteri personalizzati, è possibile ottenere ulteriori informazioni sulla gestione dei criteri in questo collegamento: [gestire i criteri per i team in Microsoft teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Criteri di messaggistica

La messaggistica o la chat può anche essere gestita tramite il criterio globale predefinito oppure tramite criteri personalizzati e questo può consentire agli utenti di comunicare tra loro in un modo appropriato per la propria organizzazione. Tali informazioni possono essere esaminate in [Managing Messaging policys in teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Criteri di riunione

Nessuna discussione sui team verrebbe completata senza pianificare e implementare i criteri per le riunioni dei team. Le riunioni sono un componente essenziale dei team, che consente alle persone di soddisfare e presentare formalmente a numerosi utenti contemporaneamente, nonché di condividere contenuti rilevanti per la riunione. L'impostazione dei criteri corretti per l'organizzazione attorno alle riunioni è essenziale.

Per ulteriori informazioni, vedere [Manage meeting Policies in teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) .

### <a name="app-permission-policies"></a>Criteri di autorizzazione delle app

I team consentono inoltre di utilizzare le app in vari punti, ad esempio i canali o le chat personali. Disporre di criteri per l'aggiunta e l'utilizzo delle app e in cui è essenziale mantenere un ambiente ricco di contenuti che sia anche sicuro.

Per ulteriori informazioni sui criteri di autorizzazione delle app, vedere [gestire i criteri di autorizzazione delle app in Microsoft teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Passaggi successivi

![Passaggio 4: criteri per le app cloud di Microsoft 365](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

