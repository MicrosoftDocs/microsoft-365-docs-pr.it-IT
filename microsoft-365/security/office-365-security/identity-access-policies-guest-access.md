---
title: Criteri di identità e accesso ai dispositivi per consentire l'accesso B2B degli utenti guest ed esterni - Microsoft 365 per le aziende | Microsoft Docs
description: Descrive l'accesso condizionale consigliato e i criteri correlati per proteggere l'accesso di utenti guest e utenti esterni.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932611"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Criteri per consentire l'accesso guest e l'accesso degli utenti esterni B2B

In questo articolo viene illustrata la modifica dei criteri di accesso alle identità e ai dispositivi consigliati per consentire l'accesso a utenti guest e esterni che dispongono di un account Business-to-Business (B2B) di Azure Active Directory (Azure AD). Queste indicazioni si basano sui [criteri comuni di identità e accesso ai dispositivi.](identity-access-policies.md)

Questi suggerimenti sono progettati per essere applicati al livello **di** protezione di base. Tuttavia, è anche possibile modificare i suggerimenti in base alle esigenze specifiche per la **protezione sensibile** **e altamente regolamentata.**

Fornire un percorso per l'autenticazione degli account B2B con il tenant di Azure AD non consente a questi account di accedere all'intero ambiente. Gli utenti B2B e i relativi account hanno accesso a servizi e risorse, come i file, condivisi con loro dai criteri di accesso condizionale.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Aggiornamento dei criteri comuni per consentire e proteggere gli utenti guest e gli utenti esterni

Questo diagramma mostra quali criteri aggiungere o aggiornare tra i criteri comuni di identità e accesso ai dispositivi, per l'accesso degli utenti guest ed esterni B2B.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso guest](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Vedere una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

Nella tabella seguente sono elencati i criteri che è necessario creare e aggiornare. I criteri comuni sono associati alle istruzioni di configurazione [nell'articolo Criteri comuni di](identity-access-policies.md) identità e accesso ai dispositivi.

|Livello di protezione|Criteri|Altre informazioni|
|---|---|---|
|**Protezione di base**|[Richiedere l'autenticazione a più fattori sempre per utenti guest e esterni](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Creare questo nuovo criterio e configurare: <ul><li>Per **Assegnazioni > utenti** e gruppi >, scegliere Seleziona utenti e gruppi e quindi selezionare Tutti gli utenti guest ed **esterni.** </li><li>Per **Le assegnazioni > condizioni >** accesso , lasciare deselezionate tutte le opzioni per applicare sempre l'autenticazione a più fattori (MFA).</li></ul>|
||[Richiedere l'autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modificare questo criterio per escludere utenti guest ed esterni.|
||[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Modificare questo criterio per escludere utenti guest ed esterni.|

Per includere o escludere utenti guest e utenti esterni nei criteri di accesso condizionale, per Assegnazioni **> Utenti** e gruppi > Includi o Escludi , selezionare Tutti gli utenti guest ed **esterni.** 

![acquisizione schermo di controlli per l'esclusione di utenti guest ed esterni](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Altre informazioni

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Accesso degli utenti guest e esterni con Microsoft Teams

Microsoft Teams definisce gli utenti seguenti:

- **L'accesso** guest usa un account B2B di Azure AD che può essere aggiunto come membro di un team e avere accesso alle comunicazioni e alle risorse del team.

- **L'accesso** esterno è per un utente esterno che non dispone di un account B2B. L'accesso degli utenti esterni include inviti, chiamate, chat e riunioni, ma non include l'appartenenza al team e l'accesso alle risorse del team.

Per ulteriori informazioni, vedere il confronto [tra gli utenti guest e l'accesso degli utenti esterni per i team.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)

Per ulteriori informazioni sulla protezione dei criteri di identità e accesso ai dispositivi per Teams, vedere Suggerimenti sui criteri per la protezione di [chat, gruppi e file di Teams.](teams-access-policies.md)

### <a name="require-mfa-always-for-guest-and-external-users"></a>Richiedere l'autenticazione a più fattori sempre per gli utenti guest ed esterni

Questo criterio richiede agli utenti guest di registrarsi per l'autenticazione a più fattori nel tenant, indipendentemente dal fatto che siano registrati per l'autenticazione a più fattori nel tenant principale. Quando si accede alle risorse nel tenant, gli utenti guest e esterni devono usare l'autenticazione a più fattori per ogni richiesta.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Esclusione di utenti guest ed esterni dall'autenticazione a più fattori basata sul rischio

Anche se le organizzazioni possono applicare criteri basati sul rischio per gli utenti B2B che usano Azure AD Identity Protection, esistono limitazioni nell'implementazione di Azure AD Identity Protection per gli utenti di collaborazione B2B in una directory delle risorse a causa della loro identità esistente nella home directory. A causa di queste limitazioni, Microsoft consiglia di escludere gli utenti guest dai criteri MFA basati sul rischio e di richiedere a questi utenti di usare sempre l'autenticazione a più fattori.

Per ulteriori informazioni, vedere [Limitations of Identity Protection for B2B collaboration users.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)

### <a name="excluding-guests-and-external-users-from-device-management"></a>Esclusione di utenti guest ed esterni dalla gestione dei dispositivi

Solo un'organizzazione può gestire un dispositivo. Se non si escludono utenti guest e utenti esterni dai criteri che richiedono la conformità dei dispositivi, questi criteri bloccheranno questi utenti.

## <a name="next-step"></a>Passaggio successivo

![Passaggio 4: Criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
