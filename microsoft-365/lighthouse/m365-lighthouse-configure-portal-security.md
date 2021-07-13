---
title: Configurare Microsoft 365 Lighthouse sicurezza del portale
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Per i provider di servizi gestiti (MSP) Microsoft 365 Lighthouse, informazioni su come configurare la sicurezza del portale.
ms.openlocfilehash: 1e67903fc6c3dfd4e1949ef8c3e80ad4af12ad5c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395385"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>Configurare Microsoft 365 Lighthouse sicurezza del portale

> [!NOTE]
> Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i [requisiti](m365-lighthouse-requirements.md). Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

La protezione dell'accesso ai dati dei clienti quando un provider di servizi gestiti (MSP) dispone di autorizzazioni di accesso delegate ai tenant è una priorità di cybersecurity. Microsoft 365 Lighthouse include funzionalità obbligatorie e facoltative che consentono di configurare Microsoft 365 Lighthouse sicurezza del portale.

## <a name="set-up-multifactor-authentication-mfa"></a>Configurare l'autenticazione a più fattori (MFA)

Come accennato nel post di blog [Il tuo pa$$word non ha importanza:](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)

> "La password non è importante, ma l'autenticazione a più fattori. In base ai nostri studi, il tuo account ha più del 99,9% di probabilità di essere compromesso se usi la MFA."

Quando gli utenti Microsoft 365 Lighthouse per la prima volta, gli verrà richiesto di configurare la MFA se l'account Microsoft 365 non lo ha già configurato. Gli utenti non saranno in grado di accedere a Microsoft 365 Lighthouse fino al completamento del passaggio di configurazione MFA richiesto. Per ulteriori informazioni sui metodi di autenticazione, vedere [Set up your Microsoft 365 sign-in for multifactor authentication](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

## <a name="set-up-roles-to-manage-customer-tenants"></a>Configurare i ruoli per gestire i tenant dei clienti

L'accesso ai dati e alle impostazioni del tenant dei clienti in Microsoft 365 Lighthouse è limitato ai ruoli Agente di amministrazione e Agente helpdesk dal programma Cloud Solutions Provider (CSP).

È possibile verificare quali utenti nel tenant del partner dispongono dei ruoli Agente di amministrazione e Agente helpdesk esaminando le appartenenze ai gruppi di sicurezza nella pagina [Azure AD - Tutti i](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) gruppi. Per informazioni su come assegnare ruoli del programma CSP e altre autorizzazioni agli utenti, vedere [Assegnare ruoli e autorizzazioni agli utenti.](/partner-center/permissions-overview) In qualità di msp, se non si dispone già di privilegi di accesso delegati per i tenant dei clienti, informazioni su come ottenerli nell'articolo Ottenere le autorizzazioni per gestire il servizio o la sottoscrizione di un [cliente.](/partner-center/customers-revoke-admin-privileges)

Nella tabella seguente sono elencate le diverse pagine Microsoft 365 Lighthouse e le autorizzazioni necessarie per visualizzare e agire sui dati e sulle impostazioni del tenant del cliente per i ruoli Agente amministratore e Agente supporto tecnico.<br><br>

| Microsoft 365 Lighthouse pagina | Autorizzazioni agente amministratore | Autorizzazioni dell'agente helpdesk |
|--|--|--|
| Home page | <ul><li>Visualizzare tutte le </li></ul> | <ul><li>Visualizzare tutte le </li></ul> |
| Tenant | <ul><li>Visualizzare tutte le </li><li>Aggiornare i contatti dei clienti e il sito Web</li><li>Visualizzare e applicare piani di distribuzione</li></ul> | <ul><li>Visualizzare tutte le </li><li>Aggiornare i contatti dei clienti e il sito Web</li><li>Visualizzare i piani di distribuzione</li></ul> |
| Utenti | <ul><li>Visualizzare tutte le </li><li>Reimpostare la password</li><li>Bloccare l'accesso</li><li>Abilitare l'autenticazione a più fattori</li></ul> | <ul><li>Visualizzare tutte le </li><li>Reimpostare la password</li><li>Bloccare l'accesso</li></ul> |
| Dispositivi | <ul><li>Visualizzare tutte le </li></ul> | <ul><li>Visualizzare tutte le </li></ul> |
| Minacce | <ul><li>Visualizzare tutte le </li><li>Eseguire un'analisi rapida</li><li>Eseguire l'analisi completa</li><li>Riavvia dispositivo</li><li>Aggiornare antivirus</li></ul> | <ul><li>Visualizzare tutte le </li></ul> |
| Linee di base | <ul><li>Visualizzare tutte le </li></ul> | <ul><li>Visualizzare tutte le </li></ul> |
| Integrità dei servizi | <ul><li>Visualizza tutto*</li></ul> | <ul><li>Visualizza tutto*</li></ul> |

> [!NOTE]
> Attualmente, per eseguire le azioni contrassegnate con * nella tabella, gli utenti dovranno anche disporre del ruolo Azure AD nel tenant partner con il set di proprietà **seguente: microsoft.office365.serviceHealth/allEntities/allTasks**. Per un elenco dei ruoli di Azure AD, vedere [Ruoli predefiniti di Azure AD.](/azure/active-directory/roles/permissions-reference)

Date le ampie autorizzazioni associate al ruolo Agente di amministrazione, [](/azure/active-directory/develop/secure-least-privileged-access) si consiglia di aderire al principio dell'accesso con privilegi minimi quando si designa un utente tenant partner come agente di amministrazione e agente del supporto. Un modo per eseguire questa operazione è assegnare il ruolo Dell'helpdesk Agent agli utenti del tenant partner necessari. In questo modo possono visualizzare i dati e le impostazioni dei clienti, ma non apportare modifiche generali. Quindi, se necessario, usare le funzionalità di approvazione dell'accesso just-in-time di Azure AD Privileged Identity Management (PIM) per assegnare agli utenti un ruolo agente amministratore con ambito temporale.

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Configurare Azure AD Privileged Identity Management (PIM)

Gli MSP possono ridurre al minimo il numero di persone che hanno accesso a informazioni o risorse protette tramite Azure AD Privileged Identity Management (PIM). PIM riduce la possibilità che un utente malintenzionato o utenti autorizzati accedono alle risorse o che inavvertitamente influisca su una risorsa sensibile. Gli MSP possono inoltre concedere agli utenti l'accesso con privilegi just-in-time alle risorse e monitorare le operazioni che gli utenti designati stanno eseguendo con l'accesso con privilegi.

> [!NOTE]
> L'uso di Azure AD PIM richiede una licenza Azure AD Premium P2 nel tenant partner.

I passaggi seguenti elevano gli utenti del tenant partner ai ruoli dell'agente di amministrazione con ambito temporale tramite Azure AD PIM:

1. Creare un gruppo assegnabile ai ruoli come descritto nell'articolo Creare un gruppo per l'assegnazione di [ruoli in Azure Active Directory](/azure/active-directory/roles/groups-create-eligible).

2. Passare ad [Azure AD : tutti i gruppi](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) e aggiungere il nuovo gruppo come membro del gruppo Agenti di amministrazione.

3. Configurare l'accesso con privilegi al nuovo gruppo come descritto nell'articolo Assegnare proprietari e membri idonei [per i gruppi di accesso con privilegi.](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)

Per ulteriori informazioni, vedere [Che cos'è Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="other-roles-and-permissions"></a>Altri ruoli e autorizzazioni

Nella tabella seguente sono elencati i ruoli del tenant del partner e le relative autorizzazioni associate.<br><br>

| Ruoli del tenant del partner | Autorizzazioni all'interno del tenant partner |
|--|--|
| Amministratore globale del tenant partner | <ul><li>Iscriversi per Microsoft 365 Lighthouse nella interfaccia di amministrazione di Microsoft 365.</li><li>Accettare gli emendamenti del contratto partner durante l'esperienza di prima esecuzione.</li><li>Visualizzare i tenant dei clienti nella pagina Tenant.\*</li><li>Attivare e disattivare un tenant.\*</li><li>Aggiornare i contatti dei clienti e il sito Web.\*</li><li>Creare, aggiornare ed eliminare tag.\*</li><li>Assegnare e rimuovere tag da un tenant del cliente.\*</li></ul> |
| Amministratore del tenant partner con almeno un tenant<br> Ruolo di Azure AD assegnato con il set di proprietà seguente:<br> **microsoft.office365.supportTickets/allEntities/allTasks**<br> Per un elenco dei ruoli di Azure AD, vedere [Ruoli predefiniti di Azure AD.](/azure/active-directory/roles/permissions-reference) | <ul><li>Creare Microsoft 365 Lighthouse di servizio.</li></ul> |

> [!NOTE]
> Attualmente, per eseguire le azioni contrassegnate con * nella tabella, l'amministratore globale deve assumere il ruolo agente di amministrazione.

## <a name="related-content"></a>Contenuto correlato

[Panoramica di Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (articolo)\
[Iscriversi per Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (articolo)\
[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml) (articolo)