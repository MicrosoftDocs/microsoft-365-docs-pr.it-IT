---
title: Gestione dell'accesso in Microsoft 365 groups, teams e SharePoint
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informazioni su come gestire l'accesso in Microsoft 365 gruppi, teams e SharePoint.
ms.openlocfilehash: 8b58016ffa421328e3c1442d4ed2364f2eedc37b
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662687"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Gestione dell'accesso in Microsoft 365 groups, teams e SharePoint

Sono disponibili numerosi controlli che consentono di gestire la modalità di accesso alle risorse in gruppi, team e SharePoint. Esaminare queste opzioni e valutare il modo in cui vengono mappate alle esigenze aziendali, la sensibilità dei dati e l'ambito delle persone con cui gli utenti devono collaborare.

Nella tabella seguente viene fornita una guida di riferimento rapida per i controlli di accesso disponibili in Microsoft 365. Ulteriori informazioni sono disponibili nelle sezioni seguenti.

|Categoria|Descrizione|Riferimenti|
|:-------|:----------|:--------|
|Appartenenza|||
||Individuazione di team privati|[Gestire l'individuazione di team privati in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Appartenenza a gruppi dinamici in base alle regole|[Creare o aggiornare un gruppo dinamico in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controllare gli utenti che possono condividere file, cartelle e siti.|[Configurare e gestire le richieste di accesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Accesso condizionale|||
||Autenticazione a più fattori|[Multi-Factor Authentication di Azure](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controllo dell'accesso al dispositivo basato sul gruppo, sul team o sulla sensibilità del sito.|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Limitare l'accesso al sito per i dispositivi non gestiti.|[Controllare l'accesso a SharePoint da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Controllare l'accesso ai siti in base alla posizione|[Controllare l'accesso ai dati di SharePoint e OneDrive in base al percorso di rete](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Accesso guest|||
||Consenti o blocca la condivisione di SharePoint da domini specificati.|[Limitare la condivisione di contenuto di SharePoint e OneDrive in base al dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Consenti o blocca l'appartenenza a team o gruppi da domini specificati.|[Consenti o blocca gli inviti agli utenti B2B provenienti da organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Impedire la condivisione anonima.|[Disattivare i collegamenti di tipo “Chiunque”](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Controllare le autorizzazioni per i collegamenti di accesso anonimo.|[Impostare le autorizzazioni di collegamento per tutti i collegamenti](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Controllare la scadenza dei collegamenti di condivisione anonima.|[Impostare una data di scadenza per i collegamenti Chiunque](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Controllare il tipo di collegamento di condivisione visualizzato per impostazione predefinita per gli utenti.|[Modificare il tipo di collegamento predefinito per un sito](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Limitare la condivisione esterna a specifiche persone.|[Limitare la condivisione esterna ai gruppi di sicurezza specificati](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controllare l'accesso Guest a un gruppo, a un team o a un sito in base alla sensibilità delle informazioni.|[Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Disattiva le opzioni di condivisione.|[Limitare la condivisione in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Gestione degli utenti|||
||Esaminare periodicamente i membri del team e del gruppo.|[Che cosa sono le recensioni di Azure AD Access?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Automatizzare la gestione degli accessi a gruppi e team.|[Che cos'è la gestione dei diritti di Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Consentire o impedire agli utenti di creare canali privati in teams.|[Gestire il ciclo di vita dei canali privati in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Appartenenza

L'appartenenza ai team e ai gruppi è controllata dai proprietari. I membri possono invitare altri utenti, ma gli inviti vengono inviati ai proprietari per l'approvazione. Mentre i gruppi e i team pubblici sono individuabili da tutti gli utenti dell'organizzazione, è possibile controllare se i team e i gruppi privati sono individuabili:

- [Gestire l'individuazione di team privati in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

È possibile gestire l'appartenenza di un gruppo o di un team in modo dinamico in base a alcuni criteri, ad esempio Department. In questo caso, i membri e i proprietari non possono invitare persone al team.

- [Creare o aggiornare un gruppo dinamico in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

I siti di SharePoint offrono la possibilità di aggiungere proprietari, membri e visitatori a parte l'appartenenza al gruppo o al team. A seconda dei requisiti, è possibile che si desideri limitare gli utenti che possono invitare persone al sito. Inoltre, a seconda della sensibilità delle informazioni in un determinato sito, è possibile limitare gli utenti che possono condividere file e cartelle. Queste restrizioni sono configurate dal team, dal gruppo o dal proprietario del sito:

- [Configurare e gestire le richieste di accesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Accesso condizionale

Con Microsoft 365, è possibile richiedere l'autenticazione a più fattori per entrambe le persone all'interno e all'esterno dell'organizzazione. Sono disponibili molte opzioni per le circostanze in cui le persone vengono richieste per un secondo fattore di autenticazione. Si consiglia di distribuire l'autenticazione a più fattori per l'organizzazione:

- [Multi-Factor Authentication di Azure](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Se si dispone di informazioni riservate in alcuni gruppi e team, è possibile applicare i criteri di gestione dei dispositivi basati sull'etichetta di riservatezza del gruppo o del team. È possibile bloccare l'accesso completamente dai dispositivi non gestiti o consentire l'accesso solo web limitato:

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

In SharePoint, è possibile limitare l'accesso ai siti da percorsi di rete specificati.

- [Controllare l'accesso ai dati di SharePoint e OneDrive in base al percorso di rete](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Risorse aggiuntive:

- [Pianificare una distribuzione di accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Panoramica di Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Controllare l'accesso a SharePoint da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Accesso guest

È possibile limitare gli utenti in base al dominio dell'indirizzo di posta elettronica. SharePoint offre impostazioni di restrizione del dominio specifiche dell'organizzazione e del sito. I gruppi e i team utilizzano gli elenchi Domain allow e Deny in Azure AD. Assicurarsi di configurare entrambe le impostazioni per evitare la condivisione indesiderata e garantire un'esperienza utente coerente:

- [Limitare la condivisione di contenuto di SharePoint e OneDrive in base al dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Consenti o blocca gli inviti agli utenti B2B provenienti da organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 consente la condivisione anonima dei file e delle cartelle tramite collegamenti di condivisione di *tutti gli utenti* . È possibile inoltrare collegamenti a *tutti* gli utenti e tutti gli utenti con il collegamento possono accedere all'elemento condiviso. In base alla sensibilità dei dati, valutare la modalità di utilizzo di collegamenti a *tutti gli utenti* , tra cui la disattivazione del tutto, la limitazione delle autorizzazioni di collegamento per la sola lettura o l'impostazione di una data di scadenza per essi:

- [Disattivare i collegamenti di tipo “Chiunque”](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Impostare le autorizzazioni di collegamento per tutti i collegamenti](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Impostare una data di scadenza per i collegamenti Chiunque](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Quando si condividono file o cartelle, gli utenti possono scegliere tra diversi tipi di collegamento. Per ridurre il rischio di condivisione inappropriata accidentale, è possibile modificare il tipo di collegamento predefinito presentato agli utenti quando condividono. Ad esempio, la modifica dell'impostazione predefinita dei collegamenti a *tutti* gli utenti, che consentono l'accesso anonimo ai collegamenti dell' *organizzazione* , può ridurre il rischio di una condivisione esterna indesiderata di informazioni riservate:

- [Modificare il tipo di collegamento predefinito per un sito](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Se l'organizzazione dispone di dati riservati che è necessario condividere con gli utenti, ma si è preoccupati per la condivisione inappropriata, è possibile limitare la condivisione esterna di file e cartelle ai membri dei gruppi di sicurezza specificati. In questo modo, è possibile limitare la condivisione esternamente a un gruppo specifico di persone o richiedere agli utenti di eseguire la formazione attorno a una condivisione esterna appropriata prima di aggiungerli al gruppo di sicurezza:

- [Limitare la condivisione esterna ai gruppi di sicurezza specificati](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

I gruppi e i team dispongono di impostazioni a livello di organizzazione che consentono o negano l'accesso guest. Anche se è possibile [limitare l'accesso Guest a team o gruppi specifici utilizzando Microsoft PowerShell](per-group-guest-access.md), è consigliabile eseguire questa operazione tramite un'etichetta di riservatezza. Con le etichette di riservatezza è possibile consentire o negare automaticamente l'accesso guest in base all'etichetta applicata:

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 offre svariati metodi di condivisione delle informazioni. Se si dispone di informazioni riservate e si desidera limitare la modalità di condivisione, esaminare le opzioni per la limitazione delle condivisioni:

- [Limitare la condivisione in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Risorse aggiuntive:

- [Proteggere la collaborazione con Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Creare un ambiente di condivisione guest sicuro](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare gli ospiti](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Gestione degli utenti

Quando i gruppi e i team si evolvono nell'organizzazione, è consigliabile esaminare regolarmente l'appartenenza al gruppo e al team. Questo può essere particolarmente utile per team e gruppi con un'appartenenza che cambia, quelli che contengono informazioni riservate oppure quelli che includono gli ospiti. Valutare la possibilità di configurare le recensioni di Access per questi team e gruppi:

- [Che cosa sono le recensioni di Azure AD Access?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Molte organizzazioni hanno partnership commerciali con altre organizzazioni o fornitori chiave con cui collaborano in modo approfondito. La gestione degli utenti e l'accesso alle risorse possono essere difficili da gestire in questi scenari. È consigliabile automatizzare alcune delle attività di gestione degli utenti e persino transirne alcune nell'organizzazione partner:

- [Che cos'è la gestione dei diritti di Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

I canali privati nei team consentono le conversazioni con ambito e la condivisione dei file tra un sottoinsieme di membri del team. A seconda delle esigenze aziendali specifiche, è possibile consentire o bloccare questa funzionalità.

- [Canali privati in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Gestire il ciclo di vita dei canali privati in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Risorse aggiuntive:

- [Governance dell'identità di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Argomenti correlati

[Sicurezza e conformità in Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Gestire le impostazioni di condivisione in SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Creare e gestire una rete esterna in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configurare Teams con tre livelli di protezione](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
