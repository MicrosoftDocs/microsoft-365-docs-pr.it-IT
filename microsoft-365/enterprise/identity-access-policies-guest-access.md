---
title: Criteri di identità e accesso ai dispositivi per consentire l'accesso ai clienti ed esterni B2B-Microsoft 365 per Enterprise | Documenti Microsoft
description: Descrive l'accesso condizionale consigliato e i criteri correlati per proteggere l'accesso di utenti esterni e Guest.
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
ms.openlocfilehash: 3afc818f9461ad0cc5ca65ea86d5e90f61f64d9b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327868"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Criteri per consentire l'accesso all'ospite e all'esterno B2B

In questo articolo viene descritto come modificare i criteri di identità e accesso ai dispositivi comuni consigliati per consentire l'accesso per gli utenti guest e esterni che dispongono di un account B2B di Azure Active Directory (Azure AD). Queste linee guida si basano sui [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md).

Tali raccomandazioni sono state progettate per essere applicate al livello di protezione di **base** . Tuttavia, è anche possibile modificare le raccomandazioni in base alla granularità delle proprie esigenze per una protezione **sensibile** e **altamente regolamentata** . 

Fornire un percorso per gli account B2B per l'autenticazione con il tenant di Azure AD non consente agli account di accedere all'intero ambiente. Gli utenti B2B e i loro account hanno accesso solo alle risorse condivise con essi (ad esempio i file) all'interno dei servizi concessi nei criteri di accesso condizionale.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Aggiornamento dei criteri comuni per consentire e proteggere gli ospiti e l'accesso esterno 

Per proteggere l'accesso guest e esterno con gli account di Azure AD B2B, nel diagramma seguente vengono illustrati i criteri da aggiungere o aggiornare dai criteri comuni di accesso ai dispositivi e alle identità. 

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso Guest](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Visualizzazione di una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

Nella tabella seguente sono elencati i criteri necessari per la creazione e l'aggiornamento. I criteri comuni collegano le istruzioni di configurazione associate nell'articolo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Livello di protezione|Criteri|Altre informazioni|
|:---------------|:-------|:----------------|
|**Protezione di base**|[Richiedi sempre un master per utenti esterni e Guest](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Creare il nuovo criterio e configurare: <ul><li> Per le **assegnazioni > gli utenti e i gruppi > includono**, scegliere **Seleziona utenti e gruppi**, quindi selezionare **tutti gli utenti guest ed esterni**. </li><li> Per le **assegnazioni > condizioni > l'accesso**, lasciare deselezionate tutte le opzioni per applicare sempre l'autenticazione a più fattori (AMF).</li>|
|        |[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modificare questo criterio per escludere gli utenti esterni e Guest.|
|        |[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Modificare questo criterio per escludere gli utenti esterni e Guest.|

Per includere o escludere gli utenti guest ed esterni nei criteri di accesso condizionale, per le **assegnazioni > gli utenti e i gruppi > includere** o **escludere**, controllare **tutti gli utenti guest e External**.

![acquisizione dello schermo dei controlli per l'esclusione di utenti esterni e Guest](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Altre informazioni

### <a name="guest-and-external-access-with-microsoft-teams"></a>Guest e accesso esterno con Microsoft Teams

Microsoft teams definisce quanto segue:

- **L'accesso Guest** utilizza un account di Azure ad B2B che può essere aggiunto come membro di un team e dispone di tutti gli accessi autorizzati alle comunicazioni e alle risorse del team.

- **L'accesso esterno** è per un utente esterno che non dispone di un account B2B. L'accesso esterno può includere gli inviti e la partecipazione a chiamate, chat e riunioni, ma non include l'appartenenza al team e l'accesso alle risorse del team.

Per ulteriori informazioni, vedere il [confronto tra Guest e accesso esterno per i team](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

I criteri di accesso condizionale si applicano solo all'accesso guest nei team perché è presente un account di Azure AD B2B corrispondente.

Per ulteriori informazioni sulla protezione dei criteri di identità e accesso ai dispositivi per i team [, vedere consigli sui criteri per la protezione delle chat, dei gruppi e dei file del team](teams-access-policies.md) .

### <a name="require-mfa-always-for-guest-and-external-users"></a>Richiedi sempre un master per utenti esterni e Guest
Questo criterio richiede agli utenti di registrarsi per l'AMF nel tenant, indipendentemente dal fatto che siano registrati per l'AMF nel tenant di casa. Quando si accede alle risorse del tenant, è necessario che gli utenti guest e esterni utilizzino Mae per ogni richiesta. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Esclusione di utenti esterni e Guest dall'AMF basata sui rischi
Sebbene le organizzazioni possano applicare criteri basati sui rischi per gli utenti B2B che utilizzano Azure AD Identity Protection, esistono limitazioni nell'implementazione di Azure AD Identity Protection per gli utenti di collaborazione B2B in una directory di risorse a causa della loro identità esistente nella Home Directory. A causa di queste limitazioni, Microsoft consiglia di escludere gli utenti Guest dai criteri dell'AMF basati sui rischi e richiedere a questi utenti di utilizzare sempre il Mae. 

Per ulteriori informazioni, vedere [limitazioni della protezione dell'identità per gli utenti di collaborazione B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users). 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Esclusione di utenti esterni e Guest dalla gestione dei dispositivi 
Solo un'organizzazione può gestire un dispositivo. Se non si escludono gli utenti guest e esterni dai criteri che richiedono la conformità del dispositivo, questi criteri bloccano tali utenti. 

## <a name="next-step"></a>Passaggio successivo

![Passaggio 4: criteri per le app cloud di Microsoft 365](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

