---
title: Criteri di identità e accesso ai dispositivi per consentire l'accesso degli utenti esterni e dei clienti all'utente esterno-Microsoft 365 per Enterprise | Documenti Microsoft
description: Descrive l'accesso condizionale consigliato e i criteri correlati per la protezione dell'accesso degli utenti esterni e degli ospiti.
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845077"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Criteri per consentire l'accesso degli utenti esterni e dell'utente esterno B2B

In questo articolo viene descritta la modifica dei criteri consigliati per il dispositivo e l'accesso alle identità per consentire l'accesso per gli utenti esterni e i clienti che dispongono di un account B2B di Azure Active Directory (Azure AD). Queste linee guida si basano sui [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md).

Tali raccomandazioni sono state progettate per essere applicate al livello di protezione di **base** . Tuttavia, è anche possibile modificare le raccomandazioni in base alle proprie esigenze specifiche per una protezione **sensibile** e **altamente regolamentata** .

Fornire un percorso per gli account B2B per l'autenticazione con il tenant di Azure AD non consente agli account di accedere all'intero ambiente. Gli utenti B2B e i loro account hanno accesso ai servizi e alle risorse, come i file, condivisi con il criterio di accesso condizionale.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Aggiornamento dei criteri comuni per consentire e proteggere gli ospiti e l'accesso degli utenti esterni

In questo diagramma vengono illustrati i criteri da aggiungere o aggiornare tra i criteri di identità e accesso ai dispositivi comuni, per l'accesso degli utenti esterni e dell'utente esterno.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso Guest](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Visualizzazione di una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

Nella tabella seguente sono elencati i criteri necessari per la creazione e l'aggiornamento. I criteri comuni collegano le istruzioni di configurazione associate nell'articolo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Livello di protezione|Criteri|Ulteriori informazioni|
|---|---|---|
|**Protezione di base**|[Richiedi sempre l'AMF per gli utenti esterni](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Creare il nuovo criterio e configurare: <ul><li>Per le **assegnazioni > gli utenti e i gruppi > includono**, scegliere **Seleziona utenti e gruppi**, quindi selezionare **tutti gli utenti guest ed esterni**.</li><li>Per le **assegnazioni > condizioni > l'accesso**, lasciare deselezionate tutte le opzioni per applicare sempre l'autenticazione a più fattori (AMF).</li></ul>|
||[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modificare questo criterio per escludere ospiti e utenti esterni.|
||[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Modificare questo criterio per escludere ospiti e utenti esterni.|

Per includere o escludere ospiti e utenti esterni nei criteri di accesso condizionale, per le **assegnazioni > gli utenti e i gruppi > includere** o **escludere**, controllare **tutti gli utenti guest e esterni**.

![acquisizione dello schermo dei controlli per l'esclusione di ospiti e utenti esterni](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Ulteriori informazioni

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Clienti e accesso utente esterno con Microsoft Teams

Microsoft teams definisce gli utenti seguenti:

- **Accesso Guest** utilizza un account di Azure ad B2B che può essere aggiunto come membro di un team e che ha accesso alle comunicazioni e alle risorse del team.

- **L'accesso esterno** è per un utente esterno che non dispone di un account B2B. L'accesso degli utenti esterni include gli inviti, le chiamate, le chat e le riunioni, ma non include l'appartenenza al team e l'accesso alle risorse del team.

Per ulteriori informazioni, vedere il [confronto tra gli utenti e l'accesso utente esterno per i team](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Per ulteriori informazioni sulla protezione dei criteri di identità e accesso ai dispositivi per i team, vedere [Suggerimenti per i criteri per la protezione di chat, gruppi e file di Team](teams-access-policies.md).

### <a name="require-mfa-always-for-guest-and-external-users"></a>Richiedi sempre un master per utenti esterni e Guest

Questo criterio richiede agli utenti di registrarsi per l'AMF nel tenant, indipendentemente dal fatto che siano registrati per l'AMF nel tenant di casa. Quando si accede alle risorse del tenant, è necessario che gli ospiti e gli utenti esterni utilizzino Mae per ogni richiesta.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Esclusione degli ospiti e degli utenti esterni dall'AMF basata sui rischi

Sebbene le organizzazioni possano applicare criteri basati sui rischi per gli utenti B2B che utilizzano Azure AD Identity Protection, esistono limitazioni nell'implementazione di Azure AD Identity Protection per gli utenti di collaborazione B2B in una directory di risorse a causa della loro identità esistente nella Home Directory. A causa di queste limitazioni, Microsoft consiglia di escludere gli ospiti dai criteri dell'AMF basati sui rischi e richiedere a questi utenti di utilizzare sempre il Mae.

Per ulteriori informazioni, vedere [limitazioni della protezione dell'identità per gli utenti di collaborazione B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).

### <a name="excluding-guests-and-external-users-from-device-management"></a>Esclusione di ospiti e utenti esterni dalla gestione dei dispositivi

Solo un'organizzazione può gestire un dispositivo. Se non si escludono gli ospiti e gli utenti esterni dai criteri che richiedono la conformità del dispositivo, questi criteri bloccherà tali utenti.

## <a name="next-step"></a>Passaggio successivo

![Passaggio 4: criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
