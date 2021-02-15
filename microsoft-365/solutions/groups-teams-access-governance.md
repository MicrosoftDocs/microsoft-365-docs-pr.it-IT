---
title: Governance dell'accesso a gruppi, Teams e SharePoint di Microsoft 365
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
description: Informazioni sulla governance dell'accesso nei gruppi di Microsoft 365, Teams e SharePoint.
ms.openlocfilehash: fb1bec219ef0d27c2a908f5f385185a1a70e01e1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613467"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Governance dell'accesso a gruppi, Teams e SharePoint di Microsoft 365

Sono disponibili molti controlli che consentono di controllare il modo in cui gli utenti accedono alle risorse in gruppi, team e SharePoint. Esamina queste opzioni e valuta il modo in cui si associano alle esigenze aziendali, la riservatezza dei dati e l'ambito delle persone con cui gli utenti devono collaborare.

La tabella seguente fornisce un riferimento rapido per i controlli di accesso disponibili in Microsoft 365. Ulteriori informazioni sono disponibili nelle sezioni seguenti.

|Categoria|Descrizione|Riferimenti|
|:-------|:----------|:--------|
|Appartenenza|||
||Individuazione di team privati|[Gestire l'individuazione di team privati in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Appartenenza a gruppi dinamici in base alle regole|[Creare o aggiornare un gruppo dinamico in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controllare gli utenti che possono condividere file, cartelle e siti.|[Configurare e gestire le richieste di accesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Accesso condizionale|||
||Multi-Factor Authentication|[Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controllare l'accesso ai dispositivi in base alla riservatezza del gruppo, del team o del sito.|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Limitare l'accesso al sito per i dispositivi non gestiti.|[Controllare l'accesso a SharePoint da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Controllare l'accesso al sito in base alla posizione|[Controllare l'accesso ai dati di SharePoint e OneDrive in base al percorso di rete](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Accesso guest|||
||Consentire o bloccare la condivisione di SharePoint dai domini specificati.|[Limitare la condivisione del contenuto di SharePoint e OneDrive in base al dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Consentire o bloccare l'appartenenza a team o gruppi dai domini specificati.|[Consentire o bloccare gli inviti a utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Impedire la condivisione anonima.|[Disattivare i collegamenti di tipo “Chiunque”](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Controllare le autorizzazioni per i collegamenti di accesso anonimo.|[Impostare le autorizzazioni di collegamento per i collegamenti chiunque](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Controllare la scadenza dei collegamenti di condivisione anonima.|[Impostare una data di scadenza per i collegamenti Chiunque](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Controllare il tipo di collegamento di condivisione visualizzato agli utenti per impostazione predefinita.|[Modificare il tipo di collegamento predefinito per un sito](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Limitare la condivisione esterna a utenti specifici.|[Limitare la condivisione esterna ai gruppi di sicurezza specificati](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controllare l'accesso guest a un gruppo, un team o un sito in base alla riservatezza delle informazioni.|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Disattivare le opzioni di condivisione.|[Limitare la condivisione in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Gestione degli utenti|||
||Rivedere regolarmente l'appartenenza a team e gruppi.|[Che cosa sono le verifiche di accesso di Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Automatizzare la gestione degli accessi a gruppi e team.|[Che cos'è la gestione dei diritti di Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Consentire o impedire agli utenti di creare canali privati in Teams.|[Gestire il ciclo di vita dei canali privati in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Appartenenza

L'appartenenza a team e gruppi è controllata dai proprietari. I membri possono invitare altri utenti, ma gli inviti vengono inviati ai proprietari per l'approvazione. Anche se i team e i gruppi pubblici sono individuabili da chiunque nell'organizzazione, è possibile controllare se i team privati e i gruppi sono individuabili:

- [Gestire l'individuazione di team privati in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

È possibile gestire l'appartenenza a un gruppo o a un team in modo dinamico in base ad alcuni criteri, ad esempio il reparto. In questo caso, i membri e i proprietari non possono invitare persone al team.

- [Creare o aggiornare un gruppo dinamico in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

I siti di SharePoint consentono di aggiungere proprietari, membri e visitatori oltre all'appartenenza a gruppi o team. A seconda dei requisiti, è possibile limitare gli utenti che possono invitare utenti al sito. Inoltre, a seconda della riservatezza delle informazioni in un determinato sito, è possibile limitare gli utenti che possono condividere file e cartelle. Queste restrizioni sono configurate dal proprietario del team, del gruppo o del sito:

- [Configurare e gestire le richieste di accesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Accesso condizionale

Con Microsoft 365, è possibile richiedere l'autenticazione a più fattori sia per le persone all'interno che all'esterno dell'organizzazione. Esistono molte opzioni per le circostanze in cui agli utenti viene richiesto un secondo fattore di autenticazione. È consigliabile distribuire l'autenticazione a più fattori per l'organizzazione:

- [Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Se si dispone di informazioni riservate in alcuni dei gruppi e dei team, è possibile applicare i criteri di gestione dei dispositivi in base all'etichetta di riservatezza di un gruppo o di un team. È possibile bloccare completamente l'accesso da dispositivi non gestiti o consentire solo l'accesso Web limitato:

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

In SharePoint è possibile limitare l'accesso ai siti da percorsi di rete specifici.

- [Controllare l'accesso ai dati di SharePoint e OneDrive in base al percorso di rete](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Risorse aggiuntive:

- [Pianificare una distribuzione di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Panoramica di Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Controllare l'accesso a SharePoint da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Accesso guest

È possibile limitare gli utenti guest in base al dominio del loro indirizzo di posta elettronica. SharePoint offre impostazioni di restrizione del dominio a livello di organizzazione e specifiche del sito. I gruppi e Teams usano gli elenchi di domini consentiti e non consentiti in Azure AD. Assicurarsi di configurare entrambe le impostazioni per evitare condivisioni indesiderate e garantire un'esperienza utente coerente:

- [Limitare la condivisione del contenuto di SharePoint e OneDrive in base al dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Consentire o bloccare gli inviti a utenti B2B di organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 consente la condivisione anonima di file e cartelle tramite *collegamenti* di condivisione chiunque. *Tutti* i collegamenti possono essere inoltrati e chiunque abbia il collegamento può accedere all'elemento condiviso. A seconda della riservatezza dei dati,  valuta la possibilità di regolamentare il modo in cui vengono usati i collegamenti chiunque, tra cui disattivarli completamente, limitare le autorizzazioni per i collegamenti in sola lettura o impostare una scadenza per loro:

- [Disattivare i collegamenti di tipo “Chiunque”](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Impostare le autorizzazioni di collegamento per i collegamenti chiunque](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Impostare una data di scadenza per i collegamenti Chiunque](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Quando si condividono file o cartelle, gli utenti hanno diversi tipi di collegamento tra cui scegliere. Per ridurre il rischio di condivisione accidentale inappropriata, è possibile modificare il tipo di collegamento predefinito presentato agli utenti quando condividono. Ad esempio, la  modifica dell'impostazione predefinita dai  collegamenti Chiunque , che consentono l'accesso anonimo, ai collegamenti degli utenti dell'organizzazione può ridurre il rischio di condivisione esterna indesiderata di informazioni riservate:

- [Modificare il tipo di collegamento predefinito per un sito](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Se l'organizzazione dispone di dati sensibili che è necessario condividere con gli utenti guest, ma si è preoccupati per la condivisione inappropriata, è possibile limitare la condivisione esterna di file e cartelle ai membri di gruppi di sicurezza specificati. In questo modo, è possibile limitare la condivisione esternamente a un gruppo specifico di persone o richiedere agli utenti di prendere formazione sulla condivisione esterna appropriata prima di aggiungerli al gruppo di sicurezza:

- [Limitare la condivisione esterna ai gruppi di sicurezza specificati](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

I gruppi e Teams dispongono di impostazioni a livello di organizzazione che consentono o negano l'accesso guest. Anche se è possibile limitare l'accesso guest a team o gruppi specifici tramite [Microsoft PowerShell,](per-group-guest-access.md)è consigliabile farlo tramite un'etichetta di riservatezza. Con le etichette di riservatezza è possibile consentire o negare automaticamente l'accesso guest in base all'etichetta applicata:

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 offre diversi metodi di condivisione delle informazioni. Se si dispone di informazioni riservate e si desidera limitare la modalità di condivisione, esaminare le opzioni per limitare la condivisione:

- [Limitare la condivisione in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Risorse aggiuntive:

- [Proteggere la collaborazione con Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Creare un ambiente di condivisione guest sicuro](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Abilitare la collaborazione esterna B2B e gestire chi può invitare guest](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Gestione degli utenti

Quando i gruppi e i team si evolvono nell'organizzazione, è consigliabile rivedere regolarmente l'appartenenza a team e gruppi. Ciò può risultare particolarmente utile per i team e i gruppi con un'appartenenza in evoluzione, per quelli che contengono informazioni riservate o per quelli che includono utenti guest. Valutare la possibilità di configurare le verifiche di accesso per questi team e gruppi:

- [Che cosa sono le verifiche di accesso di Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Molte organizzazioni hanno relazioni commerciali con altre organizzazioni o fornitori chiave con cui collaborano in modo approfondito. La gestione degli utenti e l'accesso alle risorse possono essere difficili da gestire in questi scenari. Prendere in considerazione l'automazione di alcune delle attività di gestione degli utenti e persino la transizione di alcune di esse all'organizzazione partner:

- [Che cos'è la gestione dei diritti di Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

I canali privati in Teams consentono conversazioni con ambito e la condivisione di file tra un sottoinsieme di membri del team. A seconda delle esigenze aziendali specifiche, è possibile consentire o bloccare questa funzionalità.

- [Canali privati in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Gestire il ciclo di vita dei canali privati in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Risorse aggiuntive:

- [Governance delle identità di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Argomenti correlati

[Procedura dettagliata per la pianificazione della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Sicurezza e conformità in Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Gestire le impostazioni di condivisione in SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Creare e gestire una rete esterna in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configurare Teams con tre livelli di protezione](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
