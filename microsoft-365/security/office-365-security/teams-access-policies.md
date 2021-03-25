---
title: Criteri di Teams consigliati - Microsoft 365 per le aziende | Documenti Microsoft
description: Descrive i criteri per i suggerimenti di Microsoft su come proteggere le comunicazioni di Teams e l'accesso ai file.
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206433"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Suggerimenti per i criteri per la protezione di chat, gruppi e file di Teams

In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per proteggere chat, gruppi e contenuti di Microsoft Teams, ad esempio file e calendari. Queste indicazioni si basano sui [criteri comuni](identity-access-policies.md)di identità e accesso ai dispositivi, con informazioni aggiuntive specifiche di Teams. Poiché Teams si integra con gli altri prodotti, vedere Anche Consigli per i criteri per la protezione di siti e file di [SharePoint](sharepoint-file-access-policies.md) e Suggerimenti per i criteri per [la protezione della posta elettronica.](secure-email-recommended-policies.md)

Questi suggerimenti si basano su tre diversi livelli di sicurezza e protezione per Teams che possono essere applicati in base alla granularità delle proprie esigenze: di base, sensibili e altamente regolamentati. Altre informazioni su questi livelli di sicurezza e sui criteri consigliati a cui fanno riferimento questi suggerimenti sono disponibili nelle configurazioni [di identità e accesso ai dispositivi.](microsoft-365-policies-configurations.md)

Ulteriori suggerimenti specifici per la distribuzione di Teams sono inclusi in questo articolo per coprire specifiche circostanze di autenticazione, anche per gli utenti esterni all'organizzazione. Dovrai seguire queste indicazioni per un'esperienza di sicurezza completa.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Introduzione a Teams prima di altri servizi dipendenti

Non è necessario abilitare i servizi dipendenti per iniziare a usare Microsoft Teams. Questi servizi "funzionano solo". Tuttavia, è necessario essere pronti a gestire i seguenti elementi correlati ai servizi:

- Gruppi di Microsoft 365
- Siti del team di SharePoint
- OneDrive for Business
- Cassette postali di Exchange
- Video in streaming e piani di Planner (se questi servizi sono abilitati)

## <a name="updating-common-policies-to-include-teams"></a>Aggiornamento dei criteri comuni per includere Teams

Per proteggere chat, gruppi e contenuto in Teams, nel diagramma seguente vengono illustrati i criteri da aggiornare dai criteri comuni di identità e accesso ai dispositivi. Per ogni criterio da aggiornare, assicurati che Teams e i servizi dipendenti siano inclusi nell'assegnazione delle app cloud.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso a Teams e ai relativi servizi dipendenti](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Questi servizi sono i servizi dipendenti da includere nell'assegnazione delle app cloud per Teams:

- Microsoft Teams
- SharePoint e OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (registrazioni delle riunioni)
- Microsoft Planner (attività di Planner e dati del piano)

In questa tabella sono elencati i criteri che devono essere rivisitato e i collegamenti a ogni criterio nei criteri di identità e di accesso ai dispositivi [comuni,](identity-access-policies.md)con il criterio più ampio impostato per tutte le applicazioni di Office.

|Livello di protezione|Criteri|Ulteriori informazioni per l'implementazione di Teams|
|---|---|---|
|**Protezione di base**|[Richiedi autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Assicurati che Teams e i servizi dipendenti siano inclusi nell'elenco delle app. Teams include anche regole di accesso guest e di accesso esterno da prendere in considerazione, per ulteriori informazioni su queste regole più avanti in questo articolo.|
||[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Includere Teams e i servizi dipendenti nell'assegnazione delle app cloud.|
||[Gli utenti a rischio elevato devono modificare la password](identity-access-policies.md#high-risk-users-must-change-password)|Forza gli utenti di Teams a modificare la password durante l'accesso se vengono rilevate attività ad alto rischio per il proprio account. Assicurati che Teams e i servizi dipendenti siano inclusi nell'elenco delle app.|
||[Applicare criteri di protezione dei dati APP](identity-access-policies.md#apply-app-data-protection-policies)|Assicurati che Teams e i servizi dipendenti siano inclusi nell'elenco delle app. Aggiorna i criteri per ogni piattaforma (iOS, Android, Windows).|
||[Definire i criteri di conformità dei dispositivi](identity-access-policies.md#define-device-compliance-policies)|Includere Teams e i servizi dipendenti in questo criterio.|
||[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere Teams e i servizi dipendenti in questo criterio.|
|**Sensibili**|[Richiedi autenticazione a più fattori quando il rischio di accesso è *basso,* *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams include anche regole di accesso guest e di accesso esterno da prendere in considerazione, per ulteriori informazioni su queste regole più avanti in questo articolo. Includere Teams e i servizi dipendenti in questo criterio.|
||[Richiedere PC e *dispositivi* mobili conformi](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere Teams e i servizi dipendenti in questo criterio.|
|**Riservatezza elevata**|[*Richiedi* sempre MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Indipendentemente dall'identità dell'utente, l'autenticazione a più fattori verrà utilizzata dall'organizzazione. Includere Teams e i servizi dipendenti in questo criterio. |
|

## <a name="teams-dependent-services-architecture"></a>Architettura dei servizi dipendenti da Teams

Per riferimento, nel diagramma seguente vengono illustrati i servizi su cui si basa Teams. Per ulteriori informazioni e illustrazioni, vedere Microsoft Teams e i servizi di [produttività correlati in Microsoft 365 per architetti IT.](../../solutions/productivity-illustrations.md)

[![Diagramma che mostra le dipendenze di Teams da SharePoint, OneDrive for Business ed Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Vedi una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Accesso guest ed esterno per Teams

Microsoft Teams definisce i tipi di accesso seguenti:

- **L'accesso** guest usa un account B2B di Azure AD per un utente guest o esterno che può essere aggiunto come membro di un team e avere tutti gli accessi autorizzati alle comunicazioni e alle risorse del team.

- **L'accesso** esterno è per un utente esterno che non dispone di un account B2B di Azure AD. L'accesso esterno può includere inviti e partecipazione a chiamate, chat e riunioni, ma non include l'appartenenza al team e l'accesso alle risorse del team.

I criteri di accesso condizionale si applicano solo all'accesso guest in Teams perché esiste un account B2B di Azure AD corrispondente.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Per i criteri consigliati per consentire l'accesso per utenti guest ed esterni con un account B2B di Azure AD, vedere Criteri per consentire l'accesso [all'account B2B guest](identity-access-policies-guest-access.md)ed esterno.

### <a name="guest-access-in-teams"></a>Accesso guest in Teams

Oltre ai criteri per gli utenti interni all'azienda o all'organizzazione, gli amministratori possono consentire l'accesso guest per consentire agli utenti esterni all'azienda o all'organizzazione di accedere alle risorse di Teams e interagire con gli utenti interni per attività quali conversazioni di gruppo, chat e riunioni.

Per ulteriori informazioni sull'accesso guest e su come implementarlo, vedere [Accesso guest di Teams.](/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Accesso esterno in Teams

L'accesso esterno a volte è confuso con l'accesso guest, quindi è importante essere chiari che questi due meccanismi di accesso non interni sono diversi tipi di accesso.

L'accesso esterno consente agli utenti di Teams di un intero dominio esterno di trovare, chiamare, chattare e configurare riunioni con gli utenti in Teams. Gli amministratori di Teams configurano l'accesso esterno a livello di organizzazione. Per ulteriori informazioni, vedere [Manage external access in Microsoft Teams.](/microsoftteams/manage-external-access)

Gli utenti con accesso esterno hanno meno accesso e funzionalità rispetto a un utente aggiunto tramite accesso guest. Ad esempio, gli utenti di accesso esterno possono chattare con gli utenti interni con Teams, ma non possono accedere a canali, file o altre risorse del team.

L'accesso esterno non usa gli account utente B2B di Azure AD e pertanto non usa i criteri di accesso condizionale.

## <a name="teams-policies"></a>Criteri di Teams

Al di fuori dei criteri comuni elencati in precedenza, esistono criteri specifici di Teams che possono e devono essere configurati per gestire diverse funzionalità di Teams.

### <a name="teams-and-channels-policies"></a>Criteri di Teams e canali

Teams e canali sono due elementi di uso comune in Microsoft Teams e esistono criteri che è possibile mettere in atto per controllare cosa gli utenti possono o non possono fare quando usano team e canali. Sebbene sia possibile creare un team globale, se nell'organizzazione sono presenti o meno 5.000 utenti, è probabile che sia utile avere team e canali più piccoli per scopi specifici, in linea con le esigenze dell'organizzazione.

È consigliabile modificare i criteri predefiniti o creare criteri personalizzati ed è possibile ottenere ulteriori informazioni sulla gestione dei criteri in questo collegamento: Gestire i criteri dei team [in Microsoft Teams.](/microsoftteams/teams-policies)

### <a name="messaging-policies"></a>Criteri di messaggistica

La messaggistica, o chat, può essere gestita anche tramite i criteri globali predefiniti o personalizzati e ciò consente agli utenti di comunicare tra loro in modo appropriato per l'organizzazione. Queste informazioni possono essere esaminate in [Gestione dei criteri di messaggistica in Teams.](/microsoftteams/messaging-policies-in-teams)

### <a name="meeting-policies"></a>Criteri di riunione

Nessuna discussione su Teams sarebbe completa senza la pianificazione e l'implementazione di criteri per le riunioni di Teams. Le riunioni sono un componente essenziale di Teams, che consente alle persone di incontrarsi e presentare formalmente a molti utenti contemporaneamente e di condividere contenuti rilevanti per la riunione. L'impostazione dei criteri per l'organizzazione in base alle riunioni è essenziale.

Per ulteriori informazioni, vedere [Manage meeting policies in Teams.](/microsoftteams/meeting-policies-in-teams)

### <a name="app-permission-policies"></a>Criteri di autorizzazione delle app

Teams consente inoltre di usare le app in diverse posizioni, ad esempio canali o chat personali. Disporre di criteri per le app che possono essere aggiunte e usate e dove è essenziale per mantenere un ambiente ricco di contenuto sicuro.

Per ulteriori informazioni sui criteri di autorizzazione delle app, vedere Gestire i criteri di [autorizzazione delle app in Microsoft Teams.](/microsoftteams/teams-app-permission-policies)

## <a name="next-steps"></a>Passaggi successivi

![Passaggio 4: Criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)