---
title: Governare l'accesso Microsoft 365 gruppi, Teams e SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Informazioni sulla gestione dell'accesso in Microsoft 365 gruppi, Teams e SharePoint.
ms.openlocfilehash: 3e0485813a264fe9042e0de9596ba07e50ef72a3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538148"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Governare l'accesso Microsoft 365 gruppi, Teams e SharePoint

Esistono molti controlli che consentono di controllare il modo in cui gli utenti accedono alle risorse in gruppi, team e SharePoint. Esaminare queste opzioni e valutare il modo in cui vengono mappate alle esigenze aziendali, la riservatezza dei dati e l'ambito delle persone con cui gli utenti devono collaborare.

Nella tabella seguente viene fornito un riferimento rapido per i controlli di accesso disponibili in Microsoft 365. Nelle sezioni seguenti vengono fornite ulteriori informazioni.

|Categoria|Descrizione|Riferimenti|
|:-------|:----------|:--------|
|Appartenenza|||
||Individuazione di team privati|[Gestire l'individuazione di team privati in Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||Appartenenza a gruppi dinamici in base alle regole|[Creare o aggiornare un gruppo dinamico in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controllare chi può condividere file, cartelle e siti.|[Configurare e gestire le richieste di accesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Accesso condizionale|||
||Multi-Factor Authentication|[Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controlla l'accesso al dispositivo in base alla riservatezza di gruppi, team o siti.|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Limitare l'accesso al sito per i dispositivi non gestiti.|[Controllare SharePoint accesso da dispositivi non gestiti](/sharepoint/control-access-from-unmanaged-devices)|
||Controllare l'accesso al sito in base alla posizione|[Controllare l'accesso ai dati di SharePoint e OneDrive in base al percorso di rete](/sharepoint/control-access-based-on-network-location)|
|Accesso guest|||
||Consente o blocca SharePoint la condivisione da domini specificati.|[Limitare la condivisione di contenuti di SharePoint e di OneDrive in base al dominio](/sharepoint/restricted-domains-sharing)|
||Consentire o bloccare l'appartenenza a team o gruppi da domini specificati.|[Consentire o bloccare gli inviti agli utenti B2B da organizzazioni specifiche](/azure/active-directory/b2b/allow-deny-list)|
||Impedire la condivisione anonima.|[Disattivare i collegamenti di tipo “Chiunque”](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||Controllare le autorizzazioni per i collegamenti di accesso anonimo.|[Impostare le autorizzazioni di collegamento per i collegamenti Chiunque](./best-practices-anonymous-sharing.md#set-link-permissions)|
||Controllare la scadenza dei collegamenti di condivisione anonimi.|[Impostare una data di scadenza per i collegamenti Chiunque](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||Controlla il tipo di collegamento di condivisione visualizzato agli utenti per impostazione predefinita.|[Modificare il tipo di collegamento predefinito per un sito](/sharepoint/change-default-sharing-link)|
||Limitare la condivisione esterna a utenti specifici.|[Limitare la condivisione esterna a gruppi di sicurezza specificati](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controllare l'accesso guest a un gruppo, a un team o a un sito in base alla riservatezza delle informazioni.|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Disattiva le opzioni di condivisione.|[Limitare la condivisione in Microsoft 365](./microsoft-365-limit-sharing.md)|
|Gestione degli utenti|||
||Rivedere regolarmente l'appartenenza a team e gruppi.|[Che cosa sono le verifiche di accesso di Azure AD?](/azure/active-directory/governance/access-reviews-overview)|
||Automatizzare la gestione degli accessi a gruppi e team.|[Che cos'è la gestione dei diritti di Azure AD?](/azure/active-directory/governance/entitlement-management-overview)|
||Consentire o impedire agli utenti di creare canali privati in Teams.|[Gestire il ciclo di vita dei canali privati in Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Appartenenza

L'appartenenza a team e gruppi è controllata dai proprietari. I membri possono invitare altri utenti, ma gli inviti vengono inviati ai proprietari per l'approvazione. Anche se i team pubblici e i gruppi sono individuabili da chiunque nell'organizzazione, è possibile controllare se i team privati e i gruppi sono individuabili:

- [Gestire l'individuazione di team privati in Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

È possibile gestire l'appartenenza di un gruppo o di un team in modo dinamico in base ad alcuni criteri, ad esempio reparto. In questo caso, i membri e i proprietari non possono invitare persone al team. I gruppi dinamici utilizzano i metadati definiti in Azure Active Directory per controllare chi è un membro del gruppo. Assicurarsi che i metadati in uso siano completi e aggiornati perché i metadati non corretti possono causare l'aggiunta di utenti non corretti o di gruppi non corretti.

- [Creare o aggiornare un gruppo dinamico in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint siti consentono di aggiungere proprietari, membri e visitatori oltre all'appartenenza a gruppi o team. A seconda dei requisiti, è possibile limitare gli utenti che possono invitare persone al sito. Inoltre, a seconda della riservatezza delle informazioni in un determinato sito, è possibile limitare gli utenti che possono condividere file e cartelle. Queste restrizioni sono configurate dal team, dal gruppo o dal proprietario del sito:

- [Configurare e gestire le richieste di accesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Accesso condizionale

Con Microsoft 365, è possibile richiedere l'autenticazione a più fattori sia per le persone all'interno che all'esterno dell'organizzazione. Esistono molte opzioni per le circostanze in cui agli utenti viene richiesto di specificare un secondo fattore di autenticazione. È consigliabile distribuire l'autenticazione a più fattori per l'organizzazione:

- [Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)

Se hai informazioni riservate in alcuni dei tuoi gruppi e team, puoi applicare i criteri di gestione dei dispositivi in base all'etichetta di riservatezza di un gruppo o di un team. È possibile bloccare completamente l'accesso da dispositivi non gestiti o consentire solo l'accesso Web limitato:

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

In SharePoint, è possibile limitare l'accesso ai siti da percorsi di rete specificati.

- [Controllare l'accesso ai dati di SharePoint e OneDrive in base al percorso di rete](/sharepoint/control-access-based-on-network-location)


Risorse aggiuntive:

- [Pianificare una distribuzione di accesso condizionale](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune panoramica](/mem/intune/fundamentals/what-is-intune)

- [Controllare SharePoint accesso da dispositivi non gestiti](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Accesso guest

È possibile limitare i guest in base al dominio dell'indirizzo di posta elettronica. SharePoint offre impostazioni di restrizione del dominio a livello di organizzazione e specifiche del sito. I gruppi e Teams utilizzare gli elenchi di domini consentiti e non consentiti in Azure AD. Assicurati di configurare entrambe le impostazioni per evitare condivisioni indesiderate e garantire un'esperienza utente coerente:

- [Limitare la condivisione di contenuti di SharePoint e di OneDrive in base al dominio](/sharepoint/restricted-domains-sharing)

- [Consentire o bloccare gli inviti agli utenti B2B da organizzazioni specifiche](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 consente la condivisione anonima di file e cartelle utilizzando chiunque con *i* collegamenti di condivisione. *Tutti* i collegamenti possono essere inoltrati e chiunque abbia il collegamento può accedere all'elemento condiviso. A seconda della riservatezza dei dati,  valutare la possibilità di regolamentare l'utilizzo dei collegamenti Chiunque, inclusa la disattivazione del tutto, la limitazione delle autorizzazioni di collegamento alla sola lettura o l'impostazione di una scadenza per i collegamenti:

- [Disattivare i collegamenti di tipo “Chiunque”](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [Impostare le autorizzazioni di collegamento per i collegamenti Chiunque](./best-practices-anonymous-sharing.md#set-link-permissions)

- [Impostare una data di scadenza per i collegamenti Chiunque](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

Quando si condividono file o cartelle, gli utenti hanno diversi tipi di collegamenti tra cui scegliere. Per ridurre il rischio di condivisione accidentale inappropriata, è possibile modificare il tipo di collegamento predefinito presentato agli utenti quando condividono. Ad esempio, la modifica dell'impostazione predefinita dai  collegamenti *Chiunque* , che consentono l'accesso anonimo, ai collegamenti persone nell'organizzazione può ridurre il rischio di condivisione esterna indesiderata di informazioni riservate:

- [Modificare il tipo di collegamento predefinito per un sito](/sharepoint/change-default-sharing-link)

Se l'organizzazione dispone di dati sensibili che è necessario condividere con utenti guest, ma si è preoccupati per la condivisione inappropriata, è possibile limitare la condivisione esterna di file e cartelle ai membri dei gruppi di sicurezza specificati. In questo modo, è possibile limitare la condivisione esternamente a un gruppo specifico di persone o richiedere agli utenti di intraprendere corsi di formazione sulla condivisione esterna appropriata prima di aggiungerli al gruppo di sicurezza:

- [Limitare la condivisione esterna a gruppi di sicurezza specificati](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

I gruppi e Teams dispongono di impostazioni a livello di organizzazione che consentono o negano l'accesso guest. Sebbene sia possibile limitare l'accesso guest a team o gruppi specifici tramite [Microsoft PowerShell,](per-group-guest-access.md)è consigliabile farlo tramite un'etichetta di riservatezza. Con le etichette di riservatezza è possibile consentire o negare automaticamente l'accesso guest in base all'etichetta applicata:

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

In un ambiente in cui si invitano spesso utenti guest a gruppi e team, valutare la possibilità di configurare recensioni di accesso guest pianificate regolarmente. Ai proprietari può essere richiesto di esaminare gli utenti guest nei propri gruppi e team e approvare o negare l'accesso.

- [Configurare le verifiche di accesso per gli utenti guest](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 offre molti metodi diversi di condivisione delle informazioni. Se si dispone di informazioni riservate e si desidera limitare la modalità di condivisione, esaminare le opzioni per limitare la condivisione:

- [Limitare la condivisione in Microsoft 365](./microsoft-365-limit-sharing.md)

Risorse aggiuntive:

- [Configurare la collaborazione sicura con Microsoft 365](./setup-secure-collaboration-with-teams.md)

- [Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](./best-practices-anonymous-sharing.md)

- [Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione](./share-limit-accidental-exposure.md)

- [Creare un ambiente di condivisione guest sicuro](./create-secure-guest-sharing-environment.md)

- [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare guest](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Gestione degli utenti

Quando i gruppi e i team si evolvono nell'organizzazione, è consigliabile rivedere regolarmente l'appartenenza a team e gruppi. Ciò può risultare particolarmente utile per i team e i gruppi con un'appartenenza in evoluzione, per quelli che contengono informazioni riservate o per quelli che includono utenti guest. Valutare la possibilità di configurare le verifiche di accesso per questi team e gruppi:

- [Che cosa sono le verifiche di accesso di Azure AD?](/azure/active-directory/governance/access-reviews-overview)

Molte organizzazioni hanno relazioni commerciali con altre organizzazioni o fornitori chiave con cui collaborano in modo approfondito. La gestione degli utenti e l'accesso alle risorse possono essere difficili da gestire in questi scenari. Prendere in considerazione l'automazione di alcune delle attività di gestione degli utenti e persino la transizione di alcune di esse all'organizzazione partner:

- [Che cos'è la gestione dei diritti di Azure AD?](/azure/active-directory/governance/entitlement-management-overview)

I canali privati in Teams consentono conversazioni con ambito e condivisione di file tra un sottoinsieme di membri del team. A seconda delle esigenze aziendali specifiche, è possibile consentire o bloccare questa funzionalità.

- [Canali privati in Microsoft Teams](/MicrosoftTeams/private-channels)

- [Gestire il ciclo di vita dei canali privati in Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)

Risorse aggiuntive:

- [Azure Active Directory Governance dell'identità](/azure/active-directory/governance)

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Sicurezza e conformità in Microsoft Teams](/microsoftteams/security-compliance-overview)

[Gestire le impostazioni di condivisione in SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[Creare e gestire una rete esterna in Yammer](/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configurare Teams con tre livelli di protezione](./configure-teams-three-tiers-protection.md)